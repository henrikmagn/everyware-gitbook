---
description: 'Front, OB, notifier, update and pushing, TTLS.'
---

# Cache

## Front cache

Ledge \([https://github.com/pintsized/ledge](https://github.com/pintsized/ledge)\)

The front cache is running in nginx and in lua, it shares it's data between the instances via redis. The cache saves and serves fully generated HTML. 

It is possible to have different TTLs for different pages on the site, when the TTL has run out the cache will still return the data but with a "stale" status. The first request that gets a stale result will also trigger a background update of the cache for that key, that means that the user will get the fast cached result before the update is triggered.

The cache key can be modified to include different parameters, by default Everyware supports device detection and device type \(desktop, tablet, mobile\) is a part of the cache key. Another common parameter is auth where we want different cache keys for logged in and anonymous users.

Example of cache key specification:

{% code-tabs %}
{% code-tabs-item title="ledge-run.lua" %}
```lua
ledge:config_set("cache_key_spec", { ngx.var.every_device, ngx.var.auth, scheme, ngx.var.host, ngx.var.uri, ngx.var.args })
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Object cache

Redis Object Cache \([https://wordpress.org/plugins/redis-cache/](https://wordpress.org/plugins/redis-cache/)\)

The object cache is a Wordpress plugins, in this case it connects to redis so that the different instances can share the cached data. The plugin hooks in to the Wordpress Transients API, anything set or fetched via that API will automatically be stored in Wordpress.

Typical data stored here is JSON data that we fetch from Open Content, or data fetched from the Wordpress database.

Code example for object cache use:

{% code-tabs %}
{% code-tabs-item title="example.php" %}
```php
if ( false === ( $articles = get_transient( $cache_key ) ) ) {
                $articles = get_posts( $args );
                set_transient( $cache_key, $articles, $cache_ttl );
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}



