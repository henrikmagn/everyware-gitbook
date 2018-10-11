---
description: >-
  We have helper class for Imengine which helps you geting correct url for
  images
---

# Helper class

## Standard usage

Name of class: **Imengine**

The class is used as a static instance.

Example code:

```php
$imgSrc = Imengine::original()->quality(100)->fromUuid($uuid);
```

### Required methods: 

We have to specified src of the image so we have to add **fromUuid** or **fromSrc.**

## Static functions

### cover

**Parameters:** \( int $width = null,  int $height = null \)  
**Description:** Takes the original image ratio and customize the width or height to keep original ratio of image

### create

**Parameters:** \( array $params = \[\] \)  
**Description:** Create url from scratch by using parameters provided 

### cropResize

**Parameters:** \( int $crop\_w, int $crop\_h, int $width = null, int $height = null, int $x = 0, int $y = 0 \)  
**Description:** Crop image into defined crop-size from custom start-positions. Then scale into defined size

### fit

**Parameters:** \( int $maxsize, bool $scaleup = true \)  
**Description:** Scale image to fit inside the limits. Add scale up to make the image cover the max size-area. \(Can exceed limits on scale up\)

### hardcrop

**Parameters:** \( int $width, int $height \)   
**Description:** Crop image into defined size from top left.

### npCrop

**Parameters:** \( int $width, int $height, int $x = 0, int $y = 0, int $zoom = 1 \)  
**Description:** Crop image into defined size from custom start-positions.

### original

**Parameters:** No parameters  
**Description:** Fetch image with original size.

### thumbnail

**Parameters:** \( int $width, int $height \)  
**Description:** Crop image into defined size from center position.

### ratio

**Parameters:** \( int ****$width,  string $ratio = '3:2' \)   
**Description:** Crop image into given ratio using "hardcrop".

### autoCrop

**Parameters:** \( int $original\_width, int $original\_height, int $width, string $ratio = '3:2' \)  
**Description:** Crop image into given ratio from center.

### square

Parameters: \( int $size \)  
Description: Crop image into a square using "hardcrop".

### raw

**Parameters:** \( string $uuid, int $quality = 100 \)  
**Description:** Fetching the Raw format of the image.

## Chainable functions

### fromUuid

**Parameters:** \( string $uuid \)  
**Description:** Defines what src that Imengine will manipulate

### fromSrc

**Parameters:** \( string $imgsrc \)  
**Description:** Defines what src that Imengine will manipulate

### with

**Parameters:** \( array $params = \[\] \)  
**Description:** Add functionality to manipulation to add specific Imengine parameters through an array.

```php
$params = ['q' => 100] === ->quality(100)
```

Example of parameters to use:

```text
$params = [
    'crop_w',
    'crop_h',
    'x',
    'y',
    'width',
    'height',
    'q'
];
```

Example:

### **quality**

**Parameters:** \( int $quality \)  
**Description:** Specified quality of the manipulated image 

