# Setup

The first thing to do after activating Everyware is probably to setup the connection to Open Content. After activation a menu item should appear in the admin interface named "Open Content". By clicking on it you get to the main settings for the Everyware plugin.

#### Open Content Settings

| **Setting** | Description |
| :--- | :--- |
| Open Content | Here you will be able to set connection details such as username, password and base url to your Open Content. |
| Cache time | The time in seconds which JSON data from Open Content should be cached. |
| Log cache events | Should the cache events be logged or not, only for use in development. |
| Image service | Details for which image service to use when displaying images in admin interface, such as OC List and Everyboard articles. |
| Notifier | Setup a connection to the Open Content Notifier, it will push events to Everyware which will be used for updates of the cached data. |

#### URL Settings

| Setting | Description |
| :--- | :--- |
| Post slug | Article URL slug, defaults to "article". |
| Slug properties | Which article properties should make up the postname part of the slug. If first one is missing it will go to second and so on. |

#### Property settings

Allows for mapping of properties, if there are exceptions in property names from Everyware plugin/theme and Open Content.

#### Environment settings

| Setting | Description |
| :--- | :--- |
| Use auth | A helper boolean to set if auth is active or not. |
| Use trashed | A legacy setting that would append Open Content queries to filter out trashed articles. |
| Use nginx | Is the environment running on nginx. |
| Debug mode | Boolean for if debug mode should be active or not. |
| Everystats | Legacy setting, simple stats for article views. |
| Environment query | Add a query that will be appended to all queries that are sent to Open Content. |
| Category property | Select a property that will be used to set the value of the custom post type category in Wordpress. |
| Hierarchical properties | If articles should use parent and child categories or not. |
| Hide future articles | Whether or not articles with pubdate in the future should be hidden. |

