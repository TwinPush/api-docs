# Notifications

The _notification_ resource is the representation of a message sent to a physical device through a Push Notification.

**Available methods**

To access to the full functionality of the notification resources, the following methods are available:

| method | name | description |
|--------|------|-------------|
|<span class="label label-success">GET</span>| [show](#get-show) | obtains details from a previously created notification |
|<span class="label label-info">POST</span>| [create](#post-create) | creates a new notification to be delivered from the platform |
|<span class="label label-success">GET</span>| [report](#get-report) | obtains delivery statistics for a given notification |
|<span class="label label-success">GET</span>| [report index](#get-report-index) | obtains delivery statistics for sent notifications from a given date |
|<span class="label label-success">GET</span>| [deliveries](#get-deliveries) | obtains paginated list of deliveries for a given notification |
|<span class="label label-success">GET</span>| [inbox](#get-inbox) | retrieves the notifications sent to the user by the alias device |
|<span class="label label-success">DELETE</span>| [delete inbox](#delete-inbox-notification) | removes a notification from the inbox of the associated user |

**Model**

Notification representation objects will contain the following information:

| attribute | type | description |
|-----------|------|-------------|
| id | string | Unique identifier for the notification |
| title | string | Title to be displayed in Android notifications center or TwinPush inbox |
| alert | string | Message to be displayed in the Push Notification |
| tp\_rich\_url | string | Content URL for rich notifications |
| custom_properties | HashMap | Map of custom properties set for the notification |
| tags | String[] | List of tags set to categorize notification |
| send\_since | datetime | Date and time of scheduled sending |
| sound | string | Custom sound set to notification |
| badge | string | Modifier for device badge count |
| group_name| string | Name of the group where notification is included |
| delivery_speed | string | Defines the number of deliveries per minute when sending the notification. Available values are: `instant`, `fast`, `normal` or `slow`. |


##<span class="label label-success">GET</span> show

Returns all the details of a previously created notification.

###Request

**Path**

Find application notification from ID:

```bash
GET /apps/${app_id}/notifications/${notif_id}
```

Also for notifications received from a device:

```bash
GET /apps/${app_id}/devices/${device_id}/notifications/${notif_id}
```

**Example request**

```bash
curl -X GET \
https://{{subdomain}}.twinpush.com/api/{{version}}/devices/1a2b3c4d5f/notifications/2b3c4d5f6g
```

###Response

It returns a single notification object:

**Example response**

```javascript
{
  "id": "2b3c4d5f6g",
  "sound": null,
  "alert": "Notification message",
  "title": "Title for Android",
  "badge": "+1",
  "custom_properties": {
    "scope": "public",
    "campaign": "001"
  },
  "tp_rich_url": "http://twincoders.com/",
  "delivery_speed": "normal",
  "group_name": "API Deliveries",
  "send_since": "2016-03-01 13:34:50 UTC",
  "last_sent_at": "2016-03-01 13:34:51 UTC",
  "tags": [
    "tp_rich"
  ]
}
```

##<span class="label label-info">POST</span> create

Creates a new notification to be delivered from the platform. It requires at least the specification of the message that will be displayed and a target to be delivered to.

**Payload limit**

The maximum length for the fields of a notification is conditioned by the maximum payload size allowed for Push Services of Apple and Google:

* **iOS**: 256 bytes. Increased to 2KB for iOS7 and above.
* **Android**: 1 kilobyte

Inside this size limit it is included all the notification info that is sent to the device: title, alert, sound, badge, custom_properties, etc. 

TwinPush tries to adjust the size of the Payload by trimming the alert if needed, but is recommended to use short URLs and make a responsible use custom properties.

**Notification Target**

Each notification must have one (and only one) target parameter that defines wich devices will receive the message. Target can be defined by two different methods:

* **Simple target**: Allows to specify a list of elements of many types to be addressee of the message
* **Multiple target**: Offers the ability to customize the content of the message received by each addressee. This way each user may receive a different message customized for each within the same notification.

###Request

**Path**

```bash
POST /apps/${app_id}/notifications
```
**Headers:** To create notifications it is required to include the Application _Creator Token_ header.

```bash
X-TwinPush-REST-API-Key-Creator: ${REST_API_TOKEN_CREATOR}
Content-Type: application/json; charset: utf-8
```

**Notification params**

The parameters that define the content and category of the notification are the following:

| param | description |
|-------|-------------|
|  | **Content params** | |
|alert | The text that will be shown in the push notification received in devices. This parameter is mandatory |
|title | Notification title for Android and for TwinPush message inbox |
|url   | URL to be opened to display rich content when the user opens the notification |
|custom\_properties | Hash map of custom properties that will be reported to the user device in the notification payload
|badge | The number that the user will see in the badge indicator of the app when the notification is received (only iOS). Default value is `+1` |
|  | **Additional params** | |
|delivery\_speed | Determines the number of deliveries per minute to be send for the recipients of this notice. Slowing delivery speed will help to avoid overloading client servers due to many simultaneous app openings. Available values are:<ul><li>`instant`: will send all the notifications to the target as soon as possible</li><li>`fast`: will deliver 100.000 notifications per minute</li><li>`normal`: (default) will deliver 1.000 notifications per minute</li><li>`slow`: will deliver 100 notifications per minute</li></ul>|
|sound| The name of the file you should have as a resource in your application, and it's the one that will be played when a notification is received |
|send\_since| The time when the push notification will be sent, in format _yyyy-MM-dd HH:mm:ss Z_ |
|tags| An array of strings to categorize or differentiate in the future this notification from others |
|group\_name| Name of the group where the notification will be included. Notification Groups allows to display combined information and statistics of multiple notifications. |
|inbox| Defines whether the notification will be included or not in the notifications inbox of the user associated with the target device. |


**Simple target params**

Allows to specify a list of elements of many types to be addressee of the Push Notification:
    
| param | description | type |
|-------|-------------|------|
| broadcast | If set to `true`, the notification will be sent to all the devices registered in the application | Boolean |
| devices_ids | Array of device identifiers to be target of the notification | String[] |
| devices_aliases | Array of device alias to be target of the notification | String[] |
| segments | Devices that fulfill the conditions of any of the previously created selected segments | String[] |

**Multiple target params**

Multiple target notifications can be send through device ID or device alias:

| param | description |
|-------|-------------|
| multiple_devices | Target that allows to customize the content of the notification by device id |
| multiple_alias | Target that allows to customize the content of the notification by alias |

It is possible to customize the payload information sent to every device or alias targeted in a notification.

This is done specifying a the target through a Hash where every key is the target (device_id or alias) and the content is another hash of fields to override from the notification content parameters.

Through this method it is possible to customize the content fields of the notification received for every specified target:

| attribute | description |
|-----------|-------------|
|title|If defined, it will replace the title of the notification received by the target|
|alert|If defined, it will replace the displayed notification message|
|url|If defined, it will override the URL of the rich content|
|badge|If defined, it will override the badge indicator of the main notification|
|custom_properties|Properties defined by target will be merged with the notification properties overwriting when two keys collide|

If any of there parameters is not set, the message received by the user will contain the basic information defined in the main notification parameters.

**Example request body**

Scheduled broadcast notification:

```javascript
{
  "broadcast": true,
  "title": "Welcome to TwinPush",
  "alert": "This is the message displayed in Notifications Center",
  "url": "http://www.inception-explained.com"",
  "custom_properties": {"key1": "value1", "key2": "value2"},
  "badge": "+1",
  "delivery_speed": "slow",
  "sound": "waves",
  "send_since": "2015-10-10 15:14:33 +0000",
  "tags": ["one", "two"],
  "group_name": "Commercial Offers"
}
```
Notification by device IDs with instant delivery:

```javascript
{
  "alert": "This is the message displayed in Notifications Center",
  "devices_ids": ["1a2b3c4d5f","2b3c4d5f6g","3c4d5f6g7h"]
}
```

Notification with multiple target by alias:

```javascript
{
  "alert": "This is the message displayed in Notifications Center",
  "multiple_alias": {
    "allan_poe": { "alert": "Hi Allan, welcome to TwinPush" },
    "edgar_allan": { "alert": "Hi Edgar, welcome to TwinPush", "custom_properties": { "private": true } },
    "mike_crichton": { "alert": "Hi Mike, welcome to TwinPush", "url": "http://example.com" },
    "annonymous": {}
  }
}
```

**Example request**

```bash
curl -X POST \
  -H "X-TwinPush-REST-API-Key-Creator: ${REST_API_TOKEN_CREATOR}" \
  -H "Content-Type: application/json; charset: utf-8" \
  -d '{ 
      "alert": "Test!",
      "send_since": "2013-10-10 15:14:33 +0000",
      "url": "http://www.inception-explained.com/",
      "devices_aliases": ["john"]
      }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/notifications
```

###Response

It will return an array of notifications with a single object that represents the created notification:

**Example response**

```javascript
{
  "objects": [
    {
      "id": "2b3c4d5f6g",
      "sound": null,
      "alert": "Notification message",
      "title": "Title for Android",
      "badge": "+1",
      "custom_properties": {
        "scope": "public",
        "campaign": "001"
      },
      "tp_rich_url": "http://twincoders.com/",
      "delivery_speed": "normal",
      "group_name": "API Deliveries",
      "send_since": "2016-03-01 13:34:50 UTC",
      "last_sent_at": "2016-03-01 13:34:51 UTC",
      "tags": [
        "tp_rich"
      ]
    }
  ]
}
```

##<span class="label label-success">GET</span> report

Obtains delivery statistics for a given notification.

###Request

**Path**

```bash
GET /apps/${app_id}/notifications/${notif_id}/report
```
**Headers**

```bash
X-TwinPush-REST-API-Token: ${REST_API_TOKEN}
```

###Response

The response body contains an object with the following fields:

* **status** (string): Current status of the notification. Available values are:
    * `"draft"`: the notification has not been activated yet
    * `"sending"`: the notification is being send
    * `"sent"`: sending process has been completed
    * `"scheduled"`: the notification has been scheduled for a future send
    * `"campaign_active"`: a currently active campaign
    * `"campaign_inactive"`: a currently inactive campaign
    * `"campaign_expired"`: a finished campaign
* **delivery_count** (integer): Number of deliveries made for the notification
* **opening_count** (integer): Number of devices that did open the notification
* **errors** (object[]): List of errors reported for notification
    * platform (string): Identifier of the platform, if the error is related just with a single platform. Possible values are "ios", "android" or "all"
    * level (string): Error level. Available values are "critical", "error" or "warning"
    * key (string): Error category key
    * message (string): Detailed error description
    * created_at (datetime): Moment when the error was registered
* **notification** (object): Notification basic info

**Example response**

```javascript
{
  "status": "sent",
  "delivery_count": 82640,
  "opening_count": 17534,
  "errors": [
    {
      "platform": "ios"
      "level": "critical",
      "key": "InvalidToken",
      "message": "Provided token is not valid",
      "created_at": "2015-01-14 10:31:57 UTC",
    }
  ],
  "notification": {
    "title": "Welcome to TwinPush",
    "alert": "Welcome to the Push notification platform TwinPush",
    "badge": "+1",
    "custom_properties": {},
    "id": "12342a1234b74abc",
    "sound": "",
    "tags": [
      "tp_rich",
      "vip-inbox"
    ],
    "tp_rich_url": "http://goo.gl/kf7bgq",
    "send_since": "2014-11-07 11:24:12 UTC"
  }
}
```

##<span class="label label-success">GET</span> reports index

Returns a paginated array of notifications sent by an application. Results can be filtered by date.

###Request

**Path**

```bash
GET /apps/${app_id}/devices/${device_id}/notifications/reports
```

**Headers:** It is required to include the TwinPush Token in the `X-TwinPush-REST-API-Token` header.

 ```bash
 X-TwinPush-REST-API-Token: ${REST_API_TOKEN}
 ```

**Optional Params**

The request allows the inclusion of the following optional parameters:
    
| param | description | example |
|-------|-------------|---------|
| date | If present, it will only return notifications created since given date | "2014-04-21" or "2014-04-21T13:00:43+02:00"

**Example request**

```bash
curl -X GET \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/notifications/reports?date=2016-10-29
```

###Response

It returns a paginated array of notification report objects (see [report](#get-report)) :

**Example response**

```javascript
{
  "objects": [
    {
      "status": "sent",
      "delivery_count": 82640,
      "opening_count": 17534,
      "errors": [
        {
          "platform": "ios"
          "level": "critical",
          "key": "InvalidToken",
          "message": "Provided token is not valid",
          "created_at": "2015-01-14 10:31:57 UTC",
        }
      ],
      "notification": {
        "title": "Welcome to TwinPush",
        "alert": "Welcome to the Push notification platform TwinPush",
        "badge": "+1",
        "custom_properties": {},
        "id": "12342a1234b74abc",
        "sound": "",
        "tags": [
          "tp_rich",
          "vip-inbox"
        ],
        "tp_rich_url": "http://goo.gl/kf7bgq",
        "send_since": "2014-11-07 11:24:12 UTC"
      }
    }
  ]
}
```

##<span class="label label-success">GET</span> deliveries

Obtains paginated list of all the deliveries for a given notification. This is useful to obtain exactly who has been the recipient of the notification and also who has opened it.

###Request

**Path**

```bash
POST /apps/${app_id}/notifications/${notif_id}/deliveries
```
**Headers**

 ```bash
 X-TwinPush-REST-API-Token: ${REST_API_TOKEN}
 ```

###Response

Response body will contain a paginated array of delivery objects. Each delivery will contain the following information:

* **id** (integer): Unique identifier of the delivery
* **created_at** (datetime): moment when the notification was sent
* **open_at** (datetime): moment when the notification was open in the device. Will be `null` if user has not opened the notification
* **device** (object): Target device info

**Example response**

```javascript
{
  "offset": 0,
  "total_pages": 1,
  "total_entries": 0,
  "per_page": 30,
  "current_page": 1,
  "objects": [
    {
      "id": 45264,
      "created_at": "2016-03-01 13:34:51 UTC",
      "open_at": null,
      "device": {
        "id": "a7c9dc047d019759",
        "push_token": null,
        "last_registered_at": "2016-03-01 12:47:25 UTC",
        "created_at": "2016-03-01 12:47:25 UTC",
        "updated_at": "2016-03-01 12:47:25 UTC",
        "app_id": "816b6f7f129b5982",
        "platform": "ios",
        "language": "en_GB",
        "device_code": "iPad2",
        "device_model": "iPad 2",
        "device_manufacturer": "Apple",
        "app_version": "1.4.2",
        "sdk_version": "1.0",
        "os_version": "9.1",
        "alias_device": "user@mail.com",
        "type": "Device"
      }
    }
  ]
}
```

##<span class="label label-success">GET</span> inbox

Makes a paginated search of the notifications sent to an user through the device alias. It allows filtering by notification tags.

###Request

**Path**

```bash
GET /apps/${app_id}/devices/${device_id}/inbox
```

**Optional Params**

The request allows the inclusion of the following optional parameters:
    
| param | description | example |
|-------|-------------|---------|
| tags  | Returns notifications that contains all the given tags | `["alerts", "critical"]` |
| no_tags  | Returns notifications that does not contains any of the given tags | `["main_inbox"]` |

**Example request**

```bash
curl -X GET \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices/1a2b3c4d5f/inbox?tags[]=alerts&tags[]=critical
```

###Response

It returns a paginated array of objects that offers delivery information and wraps a notification object:

**Example response**

```javascript
{
  "objects": [
    {
      "id": "2785b9d61574e029",
      "created_at": "2016-03-01 13:34:50 UTC",
      "open_at": "2016-03-01 13:34:50 UTC",
      "notification": {
        "id": "fd99bf658771385a",
        "sound": null,
        "alert": "Notification message",
        "title": "Title for Android",
        "badge": "+1",
        "custom_properties": {
          "scope": "public",
          "campaign": "001"
        },
        "tp_rich_url": "http://twincoders.com/",
        "delivery_speed": "normal",
        "group_name": "API Deliveries",
        "send_since": "2016-03-01 13:34:50 UTC",
        "last_sent_at": "2016-03-01 13:34:51 UTC",
        "tags": ["tp_rich"],
        "type": "Notification"
      }
    }
  ]
}
```

##<span class="label label-important">DELETE</span> inbox notification

Removes the selected notification from the inbox of the user (or alias) associated to the device.

###Request

**Path**

```bash
DELETE /apps/${app_id}/devices/${device_id}/notifications/${notification_id}
```

__Example request__

```bash
curl -X DELETE \
  http://{{subdomain}}.twinpush.com/api/v2/apps/12mj18sja89/devices/1a2b3c4d5f/notifications/8a2bdm1d50
```

###Response

It will return an OK (HTTP 200) code if request is successful or a NotFound (HTTP 404) if notification can not be found.
