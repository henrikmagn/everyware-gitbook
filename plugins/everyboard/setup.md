# Setup

After the Everyboard plugin has been activated a new menu item will appear in the Wordpress admin menu. A board in itself does not do much, it has to be connected to a page before it will be rendered on the site. 

The page in itself is just a standard Wordpress page, when a board is connected to the page it will be rendered in place of the page content. Technically the Everyboard plugin hijacks the "the\_content" filter and renders it's HTML there.

#### Board Settings

| **Setting** | Description |
| :--- | :--- |
| Rendering framework | Choose framework to use when rendering the board, this determines number of columns and CSS classes used. |
| Everylist | If Everylist should be active or not. |
| OC List | If OC List should be active or not. |
| Custom CSS classes | Add custom CSS classes that can be used on row, column, article and widget types in the boards. |
| Templates | Set which teaser templates should be available for selection in the boards. |

#### List Settings

| **Setting** | Description |
| :--- | :--- |
| Published value | Set the property and it's value that says that the article is published. |
| Active items | Max amount of items that the list should be able to have active. |

#### OC List Settings

| **Setting** | Description |
| :--- | :--- |
| List query | Default query is "\*:\*", this option allows users to filter out just the lists they want to be available in the boards. There might be a specific type of lists that should be used by the sites. |
| Published property | Select the property that determines if the article is published or not. |
| Article relation property | Set the relation property to be used when fetching article data for the list. |
| Notifier | Set up a notifier listener for the lists, they require a separate listener from the article listener. |

