# OpenContent

## Standard usage

Helps you write Open Content queries.

**Name of class:** OpenContent

The class is used as a static instance.

### Default properties

Properties used in class as default values and can be overridden through functions.

```text
/**
 * Default values for making text search requests against the OCAPI class
 *
 * @var array
 */
protected static $default_search_data = [
    'q'                   => '',
    'start'               => 0,
    'limit'               => 15,
    'contenttypes'        => [],
    'properties'          => [],
    'sort.name'           => null,
    'sort.indexfield'     => null,
    'facet'               => null,
    'facet.limit'         => null,
    'facet.mincount'      => null,
    'facet.date.mincount' => null,
    'use_cache'           => true,
    'create_article'      => true
];

/**
 * Default values for fetching suggestions from OCAPI class
 *
 * @var array
 */
protected static $default_suggest_data = [
    'field'                => null,
    'q'                    => null,
    'incompleteWord'       => null,
    'incompleteWordInText' => null,
];
```

### Example code

```php
$search = OpenContent::search([
    'q' => 'contenttype:Article',
    'limit' => 1
]);

var_dump($search);

// Result:

Array
(
    [duration] => 18
    [hits] => 67
    [facet] => stdClass Object
        (
            [fields] => Array
                (
                )

        )

    [0] => OcArticle Object {...}
)
```

## Static functions

### getCacheKey

**Parameters:** \( string $key = ' ' \)  
**Description:** Return the requested key

### search

**Parameters:** \( array $options = \[\] \)  
**Description:** Function for creating text-search queries against OpenContent using OCApi

Array of options to send to Open Content.

```text
$options = [
     * @type string $q
     * @type int $start
     * @type int $limit
     * @type array[string] $contenttypes
     * @type array[string] $properties
     * @type string $sort.name
     * @type string $sort.indexfield
     * @type bool $facet
     * @type int $facet.limit
     * @type int $facet.mincount
     * @type int $facet.date.mincount
     * @type bool $use_cache
     * @type bool $create_article
];
```

### suggest

**Parameters:** \( array $args = \[\] \)  
**Description:** Function for fetching article suggestions

```text
$args = [
    * @type array[string] $field
    * @type string $q
    * @type array[string] $incompleteWord
    * @type string $incompleteWordInText
];
```

### getArticle

**Parameters:** \( string $uuid, array $properties = \[\] \)  
**Description:** Fetch single article with uuid and define properties you want

### addPropertyBlock

_alias for_ [_OpenContentQueryBuilder::propertySearch_](opencontentquerybuilder.md#propertysearch)\_\_

**Parameters:** \( string $property\_name = '', string\|array $properties, string $glue = 'OR' \)  
**Description:** Creates a Solr-block of properties with the option to change the separator

### createProperty

_alias for_ [_OpenContentQueryBuilder::createProperty_](opencontentquerybuilder.md#createproperty)\_\_

**Parameters:** \( string $property\_name = '', string\|array $properties, string $glue = 'OR' \)  
**Description:** Creates a Solr-block of properties with the option to change the separator

### 

### 

