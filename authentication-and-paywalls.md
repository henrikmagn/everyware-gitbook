# Authentication and paywalls

How have we implemented support for end user authentication and paywalls in Everyware? A short explanation and example.

Authentication of users is done in nginx with the help of Lua, this is not how it has to be done but we have found it a good and efficient way. Doing it there means we dont have to let all requests initialize PHP and Wordpress which would be a problem for performance.

So how is this done in practice? We have to make sure different cached content is delivered to users depending on their authorization status, we also have a check on a URL basis to make sure we dont run the authentication on content where it is not needed.

The authorization workflow is kickstarted in nginx configuration.

{% code-tabs %}
{% code-tabs-item title="ledge.conf" %}
```text
# Run authentication check except these filetypes.
set $ew_auth_var "closed";
set_by_lua_file $check_auth '/opt/openresty/site/lualib/check-auth.lua';

rewrite_by_lua_file '/opt/openresty/site/lualib/auth.lua';
```
{% endcode-tabs-item %}
{% endcode-tabs %}

The Lua-code that sets this variable will validate cookie data or in some other way integrate with the authorization system to determine the status of the active user. When the status is determined it will set the value of the variable.

{% code-tabs %}
{% code-tabs-item title="auth.lua" %}
```lua
-- Only check this against request that have check_auth
if ngx.var.check_auth ~= "true" then
    return
end

ngx.req.clear_header("X-EW-Auth")
ngx.req.clear_header("X-EW-AuthEnvironment")

-- TODO: Logic that integrates the authorization system to determine user status.
local ew_auth = '';

ngx.req.set_header("X-EW-Auth", ew_auth);

local cache_key = 'closed'

if ew_auth == 'true' then
    cache_key = 'open'
elseif ew_auth == 'false' then
    cache_key = 'expired'
elseif ew_auth == 'noaccess' then
    cache_key = 'noaccess'
end

ngx.var.ew_auth_var = cache_key
```
{% endcode-tabs-item %}
{% endcode-tabs %}

When the status is determined we add that variable as part of the cache key.

{% code-tabs %}
{% code-tabs-item title="ledge-run.lua" %}
```lua
ledge:config_set("cache_key_spec", { ngx.var.every_device, ngx.var.ew_auth_var, scheme, ngx.var.host, ngx.var.uri, ngx.var.args })
```
{% endcode-tabs-item %}
{% endcode-tabs %}

When a request goes all the way to PHP we will be able to read a header value to get the authorization status. This means you can make decisions to show/hide or take any other actions depending on the status and it will only be applied to users with the same authorization status.

{% code-tabs %}
{% code-tabs-item title="auth.php" %}
```php
/**
 * Check if user has access to content.
 *
 * @return bool
 */
public static function hasUserAccess() {
  return isset($_SERVER['HTTP_X_EW_AUTH']) && $_SERVER['HTTP_X_EW_AUTH'] === 'true';
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

