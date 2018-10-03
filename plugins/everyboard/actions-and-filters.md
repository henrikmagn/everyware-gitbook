# Actions and filters

## Actions {#actions}

**board\_changed\_hook**

**Parameters:** $page\_id, the id of the page that the board is connected to \(action will fire multiple times if board is connected to multiple pages\).

**Description:** This action is triggered when a board has been updated or changed in any way.

## Filters {#filters}

**ew\_content\_container\_fill**

**Parameters:** $array = \[\], starts out with an empty array and let's the developer fill it with content, mainly article objects.

**Description:** This filter let's the developer populate an array of article objects for use in a board, the array will be the data that is used when rendering "Content Containers" in a board. A typical use for this would be a automatic category page, the same board could be used and the page would use different queries to Open Content to populate the content container data with articles for a specific category.

**everylist\_iframe\_buttons**

**Parameters:** $button\_arr = \[\], an array of button data.

**Description:** This filter has an array of buttons in, with text and src of the link. The buttons will be added to the Everylist interface.

**Example:**

```text
add_filter( 'everylist_iframe_buttons', function($button_arr) {

    $button_arr[] = [
        'title' => 'Example button',
        'src'   => 'https://www.example.com/'
    ];

    return $button_arr;
} );
```

