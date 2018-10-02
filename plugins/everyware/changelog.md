# Changelog

## Version 1.7.2

### Buxfixes

* Fix TTL-error when saving search-results to cache

## Version 1.7.1

### Buxfixes

* Make sure to iterate all nested properties when formatting data for caching
* Prepare support for new cache plugin
* Add documentation for wordpress version requirements
* Removal of deprecated functionality
* Minor fixes and optimisations

### Improvement / Feature

* Add new contenttype-specific actions on notifications
* Improved content-update on search catching 

## Version 1.7.0

### Buxfixes

* Fixed typo in instructions for using custom post type slug

### Improvement / Feature

* Updated to use article pubdate as creation date instead of article created for WordPress posts
* Implement function get\_single\_object through OcApi to get OcObject from properties endpoint

## Version 1.6.0

### Improvement / Feature

* Added license file
* Added support for category, year, monthnum and day for custom post type slug

## Version 1.5.4

### Buxfixes

* Removed use of deprecated function.
* Fix for CSS collision in Open Content settings page.

### Improvement / Feature

* Added new constant \(OC\_EDIT\_URL\) to make it possible to use other OC in writeback than the one set in Everyware.

## Version 1.5.3

### Buxfixes

* Fix bug where first property isn't added to the query string

## Version 1.5.2

### Improvement / Feature

* Improved functionality for adding OC Listeners.

## Version 1.5.1

### Improvement / Feature

* Added the ability to disable taxonomy sync for article post type on Open Content push events.

## Version 1.5.0

### Improvement / Feature

* Create OCObjects from hierarchical properties.
* Update url-setter on ocArticle.
* Update OcArticle to be able to set mapped properties on it self.
* Append Fluent pattern to abstractOcObject for better handling of data.
* Updated functionality of notifier push data.
* Add filter to be able to add more content types that are considered articles.
* Add ability to set cache time for search requests via OC Connection.
* Option to use custom cache time for search method added.
* Use default properties in on OC search-requests.
* Add extra filter for required properties

### Buxfixes

* Minor fixes and optimizations
* Update handle of deprecated methods.
* Fixed issue where Open Content password would become faulty after registering a Notifier listener.

## Version 1.4.2

### Buxfixes

* Fixed issue when hierarchical categories already exist to get correct child category for the post

## Version 1.4.1

### Improvement / Feature

* Added support for hierarchical categories creations. Settings under Environment. \(Default: false\)

## Version 1.4

* Filter added to customize which properties to get from Open Content \(ew\_apply\_default\_search\_properties\), if not used defaults to "Search response" setting in Open Content.
* Pagination data added to OC Image Display when showing multiple items
* Contenttype check of object before creating article post
* Improved autoloading of classes through composer
* Article tag/cateogries are now updated during a notifier push event

## Version 1.3.3

### Improvement

* OC Meta Writer now handles 409 status from Open Content and retries object updates.
* Added support for custom content types when fetching objects via OC Connection class. 

## Version 1.3.2

### Improvement

* Better error handling of term errors during creation of categories

  **Bugfixes**

* Fixed issue with category creation sanitizing the 'name' and not only the slug

## Version 1.3.1

### Improvement

* Added caching to method that fetches sort options, used a lot in widget forms.

## Version 1.3.0

### Improvement

* Added functionality to create hierarchical section url slug
* Removed faulty footer bar
* Updated login logotype

## Bugfixes

* Fixed issue with openssl padding for passwords

## Version 1.2.9

### Improvements

* The time to live for object cache items changed to one day, also added ability to set this value from environment variable "PHP\_OBJECT\_CACHE\_TTL".

## Version 1.2.8

### Improvements

* Reworked url writeback functionality to run on all article publish events.

## Version 1.2.7

### Features

* Added new widget for fetching images stored in Open Content.

## Version 1.2.6

### Improvements/Features

* Added support for using imgix as a image source in admin interface.
* Removed settings for choosing where to store images, no internal image storing is available.

## Version 1.2.5.1

### Improvements/Features

* Updated meta writer to handle updates via notifier.
* Removed "Flush Cache"-button from environment options.

### Bugfixes

* Fixed encoding of link data before writing to Open Content.

## Version 1.2.5

### Improvements/Features

* Added functionality to write-back custom XML-data to OC on article create/update
* Updated parameter-handling for making search-requests against OC

### Bugfixes

* Fixed issue with passwords got replaced by placeholder when trying oc connection
* Fixed issue with write-back causing it to run several times

## Version 1.2.4

### Improvements/Features

* Dashboard widget for version information added.
* Updated storing of OC password, also updated config gui.
* Removed deprecated functions.
* Removed local imengine from plugin.
* Removed old obsolete notifier functionality.
* Removed old tests
* Removed front cache flusher class.
* Removed Mobile\_Detect library.

### Bugfixes

* Bugfix for empty transient and prefix key.
* Bugfix for disabled password input
* Bugfix issue with properties causing the notifier binding to graphically glitch out
* Bugfix unwanted linebreaks and spaces from article urls.

## Version 1.2.3

* Composer support added, ability to install Everyware via composer.

## Version 1.2.2

* New feature: Everyware now writes back article urls to OC when articles are published \(if enabled\).

## Version 1.2.1

* Added base path constants for loading of assets.
* Updated default cache time for data fetched Open Content, now one week.
* Updated fetching of content-type properties in admin to use public OC endpoint.

## Version 1.2

* Optimized fetching of article image ids when fetching article data.
* Added functionality that updates a posts date when it recieves a push from OC.
* OC Objects Display widget now has a fallback if no template is chosen.
* Updated validation of property value when creating article URL.
* OC API now supports Page content type.
* Added ability to set a global variable to control the start position of searches to OC.
* Added action when OC article is created, action name: "every\_article\_created".
* Query builder interface fixed.
* Added support for \[oc\_api\_base\_query\] to be used in widgets.
* Minor fixes.

## Version 1.1

* Notifier 2.0
* New cache map functionality for updating caches on notifier push
* Updated OC widget to be compatible with new WP 4.3 changes
* Updated readme.md to show versions

## Version 1.0.6

* Added new parameter to "get\_single\_article" and "text\_search" to allow users to set which properties they want to get from OC.
* Added functionality to allow users to set the custom post type slug and a "category"-slug in the Open Content settings page.
* Added functionality to allow users to set the article slug from property values in the Open Content settings page.
* Refactored Widget control into Content Manager Plugin
* Added functionality to subscribe to Open Content Notifier / flush cache when a widgets query result has changed

## Version 1.0.5

* Introduced OcObjectCollection
* Extended OcApi class
* Minor fixes

## Version 1.0.4

* Everyware plugin extended with ImEngine\'s Resize, crop and cache. Open Content admin settings extended to reflect the new functionality.
* ImEngine integrated in image.php and more methods exposed to developers.
* A base implementation of OcAPI class
* post\_title and post\_name now falls back to leadin or text \(100 chars max\) if headline doesn\'t exists

## Version 1.0.3

* OpenContent Objects Refactored\(Article, Image, Ad\). These objects are now armed with dynamic properties to fully reflect OpenContent properties

## Version 1.0.2

* Extended OpenContent Article-Object to better reflect all the properties from open content.

## Version 1.0.1

* Added WordPress version control. This functionality will disable the Every plugin and prompt user to update WordPress if the    current version of WordPress does not meet the requirements.
* Added "Change widgets" on every OC Article/All OC Articles. This makes it possible to add widgets for all Oc Article or customize on individual Article.

## Version 1.0

* First release of Every Open Content plugin for Wordpress.

