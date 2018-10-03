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

**Parameters:**  
**Description:** 

### createOcDate

**Parameters:**  
**Description:** 

### dateSpanSearch

**Parameters:**  
**Description:** 

### propertySearch

**Parameters:**  
**Description:** 

### where

**Parameters:**  
**Description:** 

### query

**Parameters:**  
**Description:** 

### text

**Parameters:**  
**Description:** 

## Chainable functions

### append

**Parameters:**  
**Description:** 

### buildQueryString

**Parameters:**  
**Description:** 

### andIf

**Parameters:**  
**Description:** 

### andIfProperty

**Parameters:**  
**Description:** 

### andIfNot

**Parameters:**  
**Description:** 

### andIfNotProperty

**Parameters:**  
**Description:** 

### orIf

**Parameters:**  
**Description:** 

### orIfProperty

**Parameters:**  
**Description:** 

### orIfNot

**Parameters:**  
**Description:** 

### orIfNotProperty

**Parameters:**  
**Description:** 

### isEmpty

**Parameters:**  
**Description:** 

### getQuery

**Parameters:**  
**Description:** 

### getText

**Parameters:**  
**Description:** 

### getSanitizedText

**Parameters:**  
**Description:** 

### prepend

**Parameters:**  
**Description:** 

### setText

**Parameters:**  
**Description:** 

### setQuery

**Parameters:**  
**Description:** 

