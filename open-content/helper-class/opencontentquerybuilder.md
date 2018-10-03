---
description: Documentation of helper class OpenContentQueryBuilder
---

# OpenContentQueryBuilder

## Standard usage

Helps you write Open Content queries.

**Name of class:** OpenContentQueryBuilder

The class is used as a static instance.

Example code:

```php
$query = OpenContentQueryBuilder::where('contenttype', 'Article')
    ->andIfNotProperty('uuid', $arrayOfUuids)
    ->buildQueryString();
```

## Static functions

### createProperty

**Parameters:** \( string $name, string $value \)  
**Description:** Create a Solr-property string.

Example:

```php
$property = OpenContentQueryBuilder::createProperty('contenttype', 'Article');

echo $property; // contenttype:Article
```

### createOcDate

**Parameters:** \( string $date = ' ' \)  
**Description:** Create a date readable by OpenContent.

Example:

```php
$date = OpenContentQueryBuilder::createOcDate('2018/10/03 08:15PM');

echo $date; // 2018-10-03T18:15:00Z
```

### dateSpanSearch

**Parameters:** \( string $property, string $from = ' ', string $to = ' ' \)  
**Description:** Create a Solr-query block indicating a date-span.

Example:

```php
$to   = EwcDate::create(2018, 10, 24);
$from = $to->copy()->subDays(21)->startOfDay();

$dateSpan = OpenContentQueryBuilder::dateSpanSearch('Pubdate', $from->toOcString(), $to->toOcString());

echo $dateSpan; // Pubdate:[2018-10-02T22:00:00Z TO 2018-10-24T14:58:48Z]
```

### propertySearch

**Parameters:** \( string $property, string\|array $values, string $glue = 'OR' \)  
**Description:** Creates a Solr-query of one or more properties with the option to change the separator

```php
$query = OpenContentQueryBuilder::propertySearch('contenttype', ['Article', 'Concept']);

echo $query; // (contenttype:Article OR contenttype:Concept)
```

### where

_alias for propertySearch_

**Parameters:** \( string $property, string\|array $values, string $glue = 'OR' \)  
**Description:** Start a query by property search.

### query

**Parameters:** \( string $query \)  
**Description:** Start a query. Can be initialed with Solr-properties or fully Solr query.

### text

**Parameters:** \( string $text \)  
**Description:** Start a query by adding text

## Chainable functions

### append

**Parameters:** \( string $query \) ****  
**Description:** Append string to query

### buildQueryString

**Parameters:** No parameters  
**Description:** Build and retrieve the finished query string

### andIf

**Parameters:** \( string $query \)  
**Description:** Append _and_ text query

### andIfProperty

**Parameters:** \( string $property, string\|array $values, string $glue = 'OR' \)  
**Description:** Append _and_ statement to query for property. 

### andIfNot

**Parameters:** \( string $query \)  
**Description:** Append _and not_ text query

### andIfNotProperty

**Parameters:** \( string $property, string\|array $values, string $glue = 'OR' \)  
**Description:** Append _and not_ statement to query for property. 

### orIf

**Parameters:** \( string $query \) ****  
**Description:** Append _or_ text query

### orIfProperty

**Parameters:** \( string $property, string\|array $values, string $glue = 'OR' \)  
**Description:** Append _or_ statement to query for property.

### orIfNot

**Parameters:** \( string $query \)  
**Description:** Append _or not_ text query

### orIfNotProperty

**Parameters:** \( string $property, string\|array $values, string $glue = 'OR' \)  
**Description:** Append _or not_ statement to query for property.

### prepend

**Parameters:** \( string $query \)  
**Description:** Prepend text query to the query

### setText

**Parameters:** \( string $query \)  
**Description:** Setter for text search

### setQuery

**Parameters:** \( string $query \)  
**Description:** Setter for query

## Functions

### isEmpty

**Parameters:** No parameters  
**Description:** Helper function to determine if the builder will generate an empty string

### getQuery

**Parameters:** No parameters  
**Description:** Getter for raw query string

### getText

**Parameters:** No parameters  
**Description:** Getter for raw text search

### getSanitizedText

**Parameters:** No parameters  
**Description:** Retrieve a sanitize version of the text where we escape characters that might make a query

