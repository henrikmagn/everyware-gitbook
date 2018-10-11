# Actions and filters

Wordpress documentation on actions and filters.

{% embed url="https://codex.wordpress.org/Plugin\_API/Action\_Reference" %}

{% embed url="https://codex.wordpress.org/Plugin\_API/Filter\_Reference" %}

## Actions

### **pre\_oc\_push\_{$contenttype}\_update**

**Parameters:** $push\_response, a associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a update event is recieved from Open Content notifier, this action fires before any data has been set to the cache.

### **oc\_push\_{$contenttype}\_update**

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a update event is recieved from Open Content notifier, this action fires after data in cache has been updated.

### ~~**oc\_push\_update**~~ **\(deprecated\)**

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a update event is recieved from Open Content notifier, this action fires after data in cache has been updated.

### **pre\_oc\_push\_{$contenttype}\_add**

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a add event is recieved from Open Content notifier, this action fires before any data has been set to the cache.

### **oc\_push\_{$contenttype}\_add**

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a add event is recieved from Open Content notifier, this action fires after data has been set to the cache.

### ~~**oc\_push\_add**~~ **\(deprecated\)** 

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a add event is recieved from Open Content notifier, this action fires after data has been set to the cache.

### **pre\_oc\_push\_{$contenttype}\_delete**

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a delete event is recieved from Open Content notifier, this action fires before any action has been taken.

### ~~**oc\_push\_delete**~~ **\(deprecated\)**

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a delete event is recieved from Open Content notifier, this action after action has been taken.

#### **oc\_push\_{$contenttype}\_delete:** 

**Parameters:** $push\_response, an associative array with eventtype, uuid and the actual json data of the push.

**Description:** Action is triggered when a delete event is recieved from Open Content notifier, this action after action has been taken.

## Filters

### **ew\_apply\_default\_search\_properties**

**Parameters:** $properties = \[\], starts out with an empty array and let's developer fill it with their property dependecies.

**Description:** This filter will run before a request is made to Open Content to let the developer adjust which properties should be fetched. It will only run if no properties were sent to the called function, if properties were specified in the function call they will be used.

### **ew\_apply\_required\_search\_properties**

**Parameters:** $properties = \[\],  ****the array is populated with properties that Everyware is dependent on, and will let the developer add project specific dependencies.

**Description:** This filter will run before a request is made to Open Content to let the developer adjust which properties is required.

### **ew\_contenttypes\_considered\_article**

**Parameters:** $contenttypes = \[\],  ****the array starts out with "article" as only value.

**Description:** This filter allows developers to add more content types that should be used as articles in the Everyware plugin.

### **ew\_notifier\_update\_{$contenttype}\_properties**

**Parameters:** $properties = \[\],  ****the array is populated with the default properties for the contenttype.

**Description:** This filter is applied when a notification event is received from Open Content Notifier, it will determine if we need to fetch more data from Open Content for the object that was notified. For example this is where you would add hierarchical properties.

### **ew\_notifier\_update\_{$contenttype}\_filter**

**Parameters:** $filter = "",  ****an empty string.

**Description:** This filter is applied when a notification event is received from Open Content Notifier, it allows developers to add a filter to use against Open Content when fetching object data after a notification.

