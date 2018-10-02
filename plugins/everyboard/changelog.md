# Changelog

## 1.6.5

### Hotfix

* Bug in handlebars that prevent settings from opening for board-elements

## 1.6.4

### Improvement / Features

* Add support for visibility/hiding of board-elements with bootstrap 4
* Update npm dependencies
* Added license file
* fix path warning from jshint in grunt-file
* fix countable bug for PHP 7.2 support
* minor fixes and optimizations

## 1.6.3

### Improvement / Features

* Added support for new drop data format from Dashboard in Everylist.

### Hotfix

* Fixed a few minor interface bugs in the Everyboard interface.
* Fixed bug that would give warning if a page did not have Everyboard meta value.
* Fixed error occuring in PHP 7.2

## 1.6.2

### Improvement / Features

* Improved fetching of articles from OC List when rendering a board.

## 1.6.1

### Improvement / Features

* Added ability to add specific notifier listener for OC List.
* Improved handling of capabilities for "list\_user" role.

## 1.6.0

### Improvement / Features

* Make sure pages don't try to render none-existing boards
* Improve rendering of boards on pages to not include trashed boards
* Improve fetching of list articles
* Improve dependency-check for Everyware plugin
* Integrate the new standalone version of Everylist in Everyboard
* Use custom cache time for OC Lists
* Use default new properties-filter for EWLists and Everyboard Admin
* Updated translation files
* Minor fixes and optimizations 

## 1.5.13

### Hotfix

* Fixed minor interface bug in Everyboard widgets for Wordpress 4.8 and later.

## 1.5.12

### Hotfix

* Improve function to search for element when binding searchbox to Everyboard structure-item.

## 1.5.11

### Feature

* Ability to add css-class to entire board.
* Added functionality to unregister templates.

### Improvement

* Improve autoloading of classes through composer.
* Logic for creating a user role with correct capabilities to manage lists in EveryList.
* Add Bootstrap 4 to the list of grid-frameworks supported by Everyboard.

### Hotfix

* Check if an object fetched from OC has "contenttype:Article" before creating a custom\_port\_type article.

## 1.5.10

### Hotfix

* Added internal cache per request for approved list items. 

## 1.5.9

### Improvements/Features

* Support for new article drop data format from Newpsilot in Everylist.

## 1.5.8

### Improvements/Features

* Property "status" no longer hardcoded as status-property in Everylist.
* Support for new article drop data format in Everylist and Everyboard.

## 1.5.7

### Improvements/Features

* Remove Twig from Everyboard and add it as a dependency via composer
* Use Composer to autoload Everyboard classes
* Add support for content-size in "Suit Grid" framework
* fix issue when rendering classes by Everyboard

## 1.5.6

### Improvements/Features

* IMPORTANT: Changed behaviour, CSS classes added to columns will now only be added to either the column or it's wrapper \(if activated\). Previously the classes would be added to both the column or the wrapper.
* Fixed caching when fetching article templates.

### Hotfix

* Fixed HTML error in board admin page.
* Fixed issue with opacity when dropping external articles directly in to a board.
* Fixed issue where newly inserted structure items would appear above settings box.

## 1.5.5

### Hotfix

* Extra error handling for list javascript when fetching articlesf from OC.

## 1.5.4

### Improvements/Features

* Added "Product" as metadata for articles in board view.

### Hotfix

* Extra error handling for list javascript when fetching imgix images.

## 1.5.3

### Hotfix

* Fix for outputting wrong class for cell in Suit grid framework

## 1.5.2

* Bugfix: When fetching articles for a list, make sure to dont fetch if count is zero.

## 1.5.1

* Added functionality to drop articles in boards via droplink \(for example to EveryList\).

## 1.5.0

Updated version management to Semantic Versioning \([http://semver.org/](http://semver.org/)\)

* Added check to everylist not to save items being fetched after drop
* Added functionality to get image templates

## 1.4.9

* Added support for using imgix as image source in admin interface.
* Removed length limit for content in structure items.

## 1.4.8.4

### Hotfix

* Fix for using correct data when force fetching a list article from external site.
* Fix bug where cache was used for fetching articles when dropped in lists.

## 1.4.8.3

### Hotfix

* Fix for not reinitializing sidebar widgets after board render.

## 1.4.8.2

### Hotfix

* Fix for bug in content container rendering.

## 1.4.8.1

### Hotfix

* Added limit to the searches for list articles and board prefetch

## 1.4.8

### Improvements/Features

* Added inactivity check for board list
* Added functionality to take environment query in consideration when working with lists
* Added close buttons to messages that didn't have any fade-timer in list admin

  **Bugfixes**

* Fixed issue when rendering lists in admin due to old -&gt; new list convertion

## 1.4.7

* Fixed bug while rendering range of list-articles

## 1.4.6

* Added Suit grid as a rendering framework to Board Settings.

## 1.4.5

* Fixed issue with sidebar on board page
* Added width calculation of widget drag on widget page
* Fixed issue with widget filter on board page
* Updated style on widget/tab
* Defaults hide wrapper settings to true
* Changed default framework to bootstrap 3

## 1.4.4

* Added content container as static widget.
* Fixed bug with widget tagging

## 1.4.3

* Fixed issue when rendering widgets after nesting linked external boards
* Fixed issue with external article drop in boards

## 1.4.2

### Improvements/Features

* Added functionality to add loaders after the initial setup of EveryTwig

  **Bugfixes**

* Fix for sidebar widget-check failing when fetching widgets from multi-site

## 1.4.1

* Fixed broken preview
* Added back compatibility to earlier versions than WP 4.6

## 1.4

### Improvements/Features

* Widget handling in board widgets updated.
* Dashboard widget with everyboard version information.
* Range feature for everylist-items.
* Custom javascript-event for board-preview reload
* Content-size classes for widgets and articles rendered by everyboard.
* Changed deprecated wp-functions

  **Bugfixes**

* Bugfix small col size bug in boards

## 1.3.3

* Improved board widgets to only load once on init
* Added functionality to only display widgets contained in the Everyboard-sidebar in boards
* Removed obsolete tests
* Removed deprecated functions
* Removed template engine options
* Removed obsolete mobile detect dependency

## 1.3.2

* Support to install plugin via composer added.
* Fixed issue with EveryList preview, also added javascript event for EveryList preview load.

## 1.3.1

* Fixed issue when rendering widgets from linked boards causing them to reinitialize all widget all the time
* Avoid unnecessary requests to Open Content if no manual articles exist when rendering board.

## 1.3

* Fixed board render class calculation bug when used with nested linked boards
* Fixed major memory leak during usage of multiple nested linked boards
* Fixed issue with embed widgets breaking during a save
* Added GIT\_COMMIT number to everytwig cache key
* Added ability to preview a list with a chosen article template
* Added ability to use shortcodes in widgets placed in sidebars
* Fixed minor issue with board upgrader

## 1.2.2

* Bug fix for networked list permalink problem if article did not exist on site
* Bug fix for list items getting wrong/no permalink when used in linked board

## 1.2.1

* Fixed bug where article settings box would appear under other gui elements in the admin interface.
* Added Bootstrap 3 - 20 columns framework, also made changes to admin to allow use of other column sizes.
* Bug fix for not generating "ghost" rows/columns when saving/applying out of settings box
* Minor fix for networked lists \(switch\_to\_blog / restore\_current\_blog\)

## 1.2

* Dependant on Everyware 1.0.7
* Added functionality to share list items over networked sites
* Added stucture items to Everylist \(caption divider\)
* Added functionality to automatically truncate Everylists after a set amount \(default: 20\)
* Improved faulty check against connection problem to OC when working with lists
* Removed articles should no longer give JS errors
* Improvement in article drop functionality

## 1.1

* Added Everylist component
* Added functionality to share board across network sites
* Added global site column-width identification
* Fixed board preview bug
* Fixed bug in version handling of boards
* Improved external article drop functionality
* Removed submit event on form in boards causing reload when searching for widgets

## 1.0

* Integrated functionality to use Twig as an rendering engine
* Board drop error handling improvements
* Board upgrade functionality added
* Added functionality to import old css structure
* Upgraded to bootstrap 3.3
* Improved board widgets page behaviour
* Removed hardcoded values and paths to the plugin
* Added board lockdown if board data is changed remotely
* Added support to use imengine in board admin
* Added functionality to handle removed articles
* Added functionality to handle articles with future pubdate
* Added languange support
* Added validation to make sure Everyware is active before activating board
* Added functionality to have multiple versions saved

## 0.3

### Board Admin Main Area

* Added support for Bootstrap 3.
* Added support for different layouts on different devices / page widths.
* Added support for hiding elements on different devices / page widths.
* Added board version support, saves the five latest versions of a board.
* Added keyboard shortcut for board publishing \(cmd+s or ctrl+s\).
* Implemented functionality to parse older board structure and convert it to the new standard.
* Fixed issue where structure item names could not contain special swedish characters.
* Fixed issue where rows were not sortable or draggable at first after being dragged in.
* Fixed issue where custom names on columns would hide the colspan.
* Fixed issue where columns were not sortable or draggable at first after being dragged in.
* Fixed issue where removed option for a structure item would apply to all devices and could not be changed.
* Article headlines are now displayed in the header of the structure item.
* Fixed issue where inherited templates would not update for newly added articles.
* Fixed issue where article templates could not include special swedish characters.
* Implemented optimization too manual article fetching, all articles are now fetched in a single request for each board.
* Redesinged the settings box.

### Board Admin Sidebar

* Added text autocompletion for article search.
* Added pubdate fields to article search.
* Added information about what page is active and total number of pages to article search.
* Added pagination for article search.
* Fixed bug where sticky effect for sidebar would not work in all browsers.
* Fixed problem where widget name would not be updated on board when settings were changed.
* Fixed bug where Linked Board didn't show all available boards.
* Fixed problem where the widget content was rendered outside the widget container on board admin.
* Added functionality to show/hide widgets filtered on their type.
* Added functionality to show/hide all widgets.
* Saved search queries are now added to the list instantly when created.
* Added pointer cursor on save search hover.
* Removed "Template" from articles in search results.

### Board Widgets

* Settings box is now removed on save.
* Fixed bug where settings box would not be populated in some cases.
* Removed clean up of board widgets if the plugin is deactivated.

## 0.2

* Initital "public" release.

