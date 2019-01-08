# Implementation of lua endpoint

For this plugin to work, the server environment must have an endpoint that answers to "/ledge-invalidate", this endpoint should invalidate the url sent to it from the cache. If you are using Everyware in a Infomaker hosted environment we have included a `example.lua` file that should work out of the box. The following instructions are for a Infomaker hosted environment with nginx/lua support.

The function needs to be initiated in the ledge-run.lua file, it could look like this:

```lua
if ngx.var.request_uri == "/ledge-invalidate/" and ngx.req.get_method() == "POST" then

    local ledgeInvalidation = require "ledge-invalidate.lua"
    ledgeInvalidation:new({
        prefix = "ledge:cache:_1_:_2_:",
        cache_key = {
            [1] = {
                "desktop",
                "tablet",
                "mobile"
            },
            [2] = {
                "open",
                "noaccess",
                "expired",
                "closed"
            }
        }
    })
end
```

