Notification System
===================

## DropHero notification interface

Message types:

| type     | Description              |
| -------: | ------------------------ |
| warning  | Warning messages that will be displayed into user control panel's log         |
| error    | Error messages that will be displayed into user control panel's log         |
| system   | System notifications (plugin installation or callback notifications)          |

### System messages

DropHero needs a way to keep in touch with their connected apps. By using system messages, this apps can notify their installation and their callback url's in order to allow DropHero start a reverse communication.

### DropHero reverse communications using

When DropHero needs initiate a communitacion with a certain user plugin (for example, there's stock changes in some user subscribed product) DropHero will use that provided callbacks. The flow is simple, DropHero make an http request on a certain callback, and the plugin triggers a call in reverse). This allows DropHero to make "push" calls instead of recurly ones. 

There's 2 types of callbacks:

| Callback type     | Action              | Description              |
| -------: | ------------------------ |
| product  | Triggers a <code>GET /v1/subscribed</code> call  | Allow DropHero to notify changes relted to products to an specific user plugin       |
| orders   | Triggers a <code>GET /v1/orders</code> call  | Allow DropHero to notify changes relted to orders to an specific user plugin      |

##Notify requests

- <code>POST /v1/notify</code> This JSON data must be serialized and attached to the request into a new variable called <code>data</code>.

```JSON
{
    "1": {
        "msgtype": "warning",
        "message": "There's something wrong here..."
    },
    "2": {
        "msgtype": "error",
        "message": "Ups, definitely something went wrong..."
    },
    "3": {
        "msgtype": "system",
        "message": "plugin installed"
       },
    "4": {
        "msgtype": "system",
        "message": {
            "callbacks_url": {
    			"orderstatus": "sdfgsdfsadf.com",
                "products": "lolailo.com/dropwidget/index/lolailo"
            }
        }
    }
}
```