# Filters

**ew\_content\_container\_cache\_query**

A filter that allows you to define queries used by content containers for the page, the filter is run in context of the page. It expects an array of queries \(strings\) to be returned.

**ew\_cache\_invalidator\_custom\_queries**

Add custom queries to be added to the plugin query data, allows users to add any queries for any urls. Example:

```php
add_filter('ew_cache_invalidator_custom_queries', function($arr) {
    $arr[] = [ 'contenttype:Article AND Example:Value', 'https://www.example.com/example/' ];
    return $arr;
});
```

