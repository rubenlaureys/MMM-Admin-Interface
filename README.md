# Magic-Mirror-Module-Admin-Interface
This an extension for the [MagicMirror²](https://github.com/MichMich/MagicMirror). This module provides an interface to manage the magic mirror and edit the configuration from your web browser.

## Installation
1. Navigate into your MagicMirror's `modules` folder and run: 
    ```
    git clone https://github.com/paviro/MMM-Callmonitor-Current-Call.git
    ```
1. Add the module to you `config.js`:
    ```
        {
        	"module": "MMM-Admin-Interface"
        },
    ```

## Usage
Go to `<HOST>:8181/MMM-Admin-Interface/` Edit away!

## Sending settings schema for other modules (Devs)
You can send your module's config schema via notification, and it will be loaded.
```javascript
let calender_schema = {
    "properties": {"modules": {"items": {"config": {"properties": {
        "calendars": {
        	"format": "tabs",
        	"options": {
        		"disable_array_delete_all_rows": true,
        		"disable_array_delete_last_row": true
        	},
        	"type": "array",
        	"items": {
        		"type": "object",
        		"headerTemplate": "Calender {{ i1 }}",
        		"properties": {
        			"symbol": {
        				"type": "string"
        			},
        			"url": {
        				"type": "string"
        			}
        		}
        	}
    }}}}}}
}
this.sendNotification ( "schema", calender_schema );
```

You can learn more on writing a settings schema for you module at [JSON Editor](https://github.com/jdorn/json-editor).

##Changlelog

### 0.1
 - Cleaning up all console.log dev calls
 - Improved front-end
 - Improved README

###0.0.2
 - Reading and writing directly to config.js
 - Accept settings schemas from other modules via notification

###0.0.1 Initial commit