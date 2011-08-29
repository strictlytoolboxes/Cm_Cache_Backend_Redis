# Zend_Cache_Backend_Redis with support for tags 

! proof of concept


## FEATURES

 - Uses the [phpredis PECL extension](https://github.com/owlient/phpredis) (requires **variadic** branch)
 - Falls-back to [redisent](https://github.com/damz/redisent) if phpredis isn't present or `use_redisent` is enabled
 - Tagging is handled using the “set” datatype for efficient tag management
 - Unit tested!

## INSTALLATION (Magento)

1. Install [redis](http://redis.io/download) (2.4 required)
2. Install [phpredis](https://github.com/nicolasff/phpredis)
** For 2.4 support you must use the "variadic" branch: `git checkout -t -b variadic origin/variadic`
** phpredis is optional, but it is much faster than Redisent
3. Install this module
** `modman rediscache clone git://github.com/colinmollenhour/Zend_Cache_Backend_Redis.git`
4. Edit app/etc/local.xml to [configure](https://gist.github.com/1172386)

## KNOWN ISSUES

 - Proper tag metadata cleanup cannot be done automatically on item expiry
 (should only be a problem if tags and ids are rarely reused and rarely cleared)

## TODO

 - Add config support for socket connection
 - Add auto-cleanup of tag metadata?

