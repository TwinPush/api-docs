# Devices

The _device_ model is a representation of a phisical device that can be registered in the TwinPush platform (like a smartphone or a tablet). Android and iOS devices are supported.

**Available methods**

To access to the full functionality of the devices resources, the following methods are available:

| method | name | description |
|--------|------|-------------|
|<span class="label label-success">GET</span>| [index](#get-index) | obtains the paginated list of application devices associated |
|<span class="label label-info">POST</span>| [register](#post-register) | create or update device registration in TwinPush |
|<span class="label label-info">POST</span>| [update badge](#post-update-badge) | updates the badge number of the device. |
|<span class="label label-info">POST</span>| [open notification](#post-open-notification) | notifies that the notification has been opened by the user |
|<span class="label label-info">POST</span>| [open app](#post-open-app) | reports that the user opened the application |
|<span class="label label-info">POST</span>| [close app](#post-close-app) | notifies that the application has been closed or went to background execution|
|<span class="label label-info">POST</span>| [update location](#post-update-location) | updates the current location of the device |
|<span class="label label-info">POST</span>| [search notifications](#post-search-device-notifications) | search of the notifications received by a device |
|<span class="label label-info">POST</span>| [set custom property](#post-set-custom-property) | assigns value for a device custom property|
|<span class="label label-important">DELETE</span>| [clear properties](#delete-clear-custom-properties) | deletes all the properties values associated with a device |

**Model**

Device resources will contain the following information:

| attribute | type | description |
|-----------|------|-------------|
| id | string | Unique identifier device in the platform |
| alias_device | string | Alias assigned to device. It is commonly used as a link with bussiness logic |
| platform | string | Physical device platform. Available values are `ios` or `android`.
| created_at | datetime | Device first registration date |
| updated_at | datetime | Device last update date. This field will change when any device usage stat is reported, and will represent the last usage time |
| last\_registered\_at | datetime | Represents the last time that the device called register service to update its token, device alias or custom properties |
| language | string | Language and region, joined by undescore |
| device_code | string | Physical device model code |
| device_model | string | Physical device commercial name |
| device_manufacturer | string | Physical device manufacturer |
| app_version | string | Client application version |
| sdk_version | string | Version of the TwinPush SDK integrated in the client application |
| os_version | string | Android or iOS Operating System version |


## <span class="label label-success">GET</span> index

Obtains the paginated list of devices associated with the given application.

### Request

**Path**

```bash
GET /apps/${app_id}/devices
```
**Headers:** It is required to include the TwinPush Token in the `X-TwinPush-REST-API-Token` header.

 ```bash
 X-TwinPush-REST-API-Token: ${REST_API_TOKEN}
 ```

**Optional Params**

The following URL parameters are optional:

| param | description |
|-------|-------------|
| date | If present, it will only return devices which registration info has changed since given date. Valid date formats are ("2014-04-21" or "2014-04-21T13:00:43+02:00"). Registration info will be considered changed when any of the following fields is updated: active, alias\_device, push\_token, custom\_properties |
| alias | If present, it will only return devices whose alias_device property match with the given parameter (ignoring case). Can be used to obtain the active devices associated to a given alias |

**Example request**

```bash
curl -X GET "https://app.twinpush.com/api/v2/apps/12mj18sja89/devices?date=2014-11-01&page=1&per_page=50" \
  -H "X-TwinPush-REST-API-Token: xxxx
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices
```

### Response

Response body will contain the array of application devices that match the included filters (if any).

**Example response**

```javascript
{
  "objects": [
    {
      "id": "a7c9dc0555019759",
      "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",
      "last_registered_at": "2016-03-01 12:47:25 UTC",
      "created_at": "2016-03-01 12:47:25 UTC",
      "updated_at": "2016-03-01 12:47:25 UTC",
      "app_id": "816b6f7f555b5982",
      "platform": "ios",
      "language": "en_GB",
      "device_code": "iPad2",
      "device_model": "iPad 2",
      "device_manufacturer": "Apple",
      "app_version": "1.4.2",
      "sdk_version": "1.0",
      "os_version": "9.1",
      "alias_device": "techie4",
      "type": "Device"
    }
  ],
  "references": []
}
```

## <span class="label label-info">POST</span> register

Creates or updates the subscription of a device in the platform.

### Request

**Path**

```bash
POST /apps/${app_id}/devices/register
```

**Headers:** To launch this request it is needed to include the TwinPush Token in the `X-TwinPush-REST-API-Token` header.

 ```bash
 X-TwinPush-REST-API-Token: ${REST_API_TOKEN}
 Content-Type: application/json; charset: utf-8
 ```

**Required params**

The register request requires the following parameters:

| param | description |
|-------|-------------|
| udid  | unique identifier of the device per application and platform. A good choice is the [ANDROID_ID](http://developer.android.com/reference/android/provider/Settings.Secure.html#ANDROID_ID) for Android and the [identifierForVendor](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIDevice_Class/index.html#//apple_ref/occ/instp/UIDevice/identifierForVendor) for iOS |
| platform | Device platform. Available values are: `"ios"` for Apple iOS devices and `"android"` for Google Android devices
| push_token | Token provided for the device by the Push notification services (known as _registrationId_ for Android and _token_ for iOS). If the push token is not provided, the device will not receive push notifications, but it will be able to report usage statistics.

**Optional Params**

Register service accepts some optional parameters that can be included or not in the request body. The associated properties to each param will be set to null if value is empty and will be ignored if not present in the request.

| param     | description | example |
|-----------|-------------|---------|
| alias_device | Value to associate the device to a user of the client platform | `"username"`
| language  | Language and region, joined by undescore | `"en_ES"`, `"en_GB"` |
| device_code | Device model code | `"osprey_umts"` |
| device_model | Device commercial name | `"iPad 2"`, `"iPhone 6S"` |
| device_manufacturer | Manufacturer | `"Apple"`, `"Samsung"` |
| app_version | Client application version | `"1.0"`, `"2.0.1"` |
| sdk_version | TwinPush SDK version | `"2.0.3"`, `"3.1"`  |
| os_version | OS (Android or iOS) version | `"9.1"`, `"5.1"` |

**Example request body**

```javascript
{
  "udid": "002ebf12a1255ddfa73967c3c5d20177",
  "platform": "ios",
  "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",
  "alias_device": "techie4",
  "platform": "ios",
  "language": "en_GB",
  "device_code": "iPad2",
  "device_model": "iPad 2",
  "device_manufacturer": "Apple",
  "app_version": "1.4.2",
  "sdk_version": "1.0",
  "os_version": "9.1"
}
```
```javascript
{
  "udid": "f12a1255ddfjd123",
  "platform": "android",
  "push_token": "APA91bHPRgkF3JUikC4ENAHEeMrd41Zxv3hVZjv9YtT8OvPWGJhQMRK3rZuJEcl7B38q",
  "alias_device": "techie4"
}
```

**Example request**

```bash
curl -X POST \
  -H "X-TwinPush-REST-API-Token: ${REST_API_TOKEN}" \
  -H "Content-Type: application/json; charset: utf-8" \
  -d '{ "udid": "002ebf12a1255ddfa73967c3c5d20177", "platform": "ios", "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",  "alias_device": "techie4"}' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices/register
```

### Response

The request will return an array of Device objects that will only contain the created (or updated) device.

The `id` value of the device will be necessary to identify the device in subsequent requests.

**Example response**

```javascript
{
  "objects": [
    {
      "id": "a7c9dc0555019759",
      "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",
      "last_registered_at": "2016-03-01 12:47:25 UTC",
      "created_at": "2016-03-01 12:47:25 UTC",
      "updated_at": "2016-03-01 12:47:25 UTC",
      "app_id": "816b6f7f555b5982",
      "platform": "ios",
      "language": "en_GB",
      "device_code": "iPad2",
      "device_model": "iPad 2",
      "device_manufacturer": "Apple",
      "app_version": "1.4.2",
      "sdk_version": "1.0",
      "os_version": "9.1",
      "alias_device": "techie4",
      "type": "Device"
    }
  ],
  "references": []
}
```

## <span class="label label-info">POST</span> update badge

Updates the badge number of a device.

### Request

**Path**

 ```bash
 POST /apps/:app_id/devices/:device_id/update_badge
 ```
**Headers**

 ```bash
 Content-Type: application/json; charset: utf-8
 ```

**Required params**

Update badge request requires a single parameter:

| param | description |
|-------|-------------|
| badge | New value for device badge |

Depending on the value set the behavior may change:

|  value  | description | example |
|---------|-------------|---------|
| numeric | The badge will be updated to given value | `0`, `1` |
| plus sign and number | Device badge will be incremented by given amount | `"+1"`, `"+2"` |
| minus sign and number | Device badge will be decreased by given amount | `"-1"`, `"-2"` |

If the result value is negative it will be set to 0.

**Example request body**

```javascript
{
  "badge": "+1"
}
```

__Example request__

```bash
curl -X POST \
  -H "Content-Type: application/json; charset: utf-8" \
  -d '{ "badge": 12 }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/update_badge
```

### Response

It will return an OK (HTTP 200) code if request is successful.

## <span class="label label-info">POST</span> open notification

Notifies that the user interacted with a sent Notification (usually opened fom notifications center). It is usefull to determine the success of a sent notification based on its opening rate.

### Request

**Path**

 ```bash
 POST /apps/${app_id}/devices/${device_id}/notifications/${notif_id}/open_notification
 ```

__Example request__

```bash
curl -X POST \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/notifications/1441befd34f112/open_notification
```

### Response

It will return an OK (HTTP 200) code if request is successful.

## <span class="label label-info">POST</span> open app

Notifies that the user opened the application. This info is used for statistics and activity reports and it is important to determinate wether a device is active or inactive for license limit purposes.

### Request

**Path**

```bash
POST /apps/${app_id}/devices/${device_id}/open_app
```

**Example request**

```bash
curl -X POST \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/open_app
```

### Response

It will return an OK (HTTP 200) code if request is successful.

## <span class="label label-info">POST</span> close app

Notifies that the application has been closed or went to background. This info is used for statistics and activity reports.

### Request

**Path**

```bash
POST /apps/${app_id}/devices/${device_id}/close_app
```

**Example request**

```bash
curl -X POST \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/close_app
```

### Response

It will return an OK (HTTP 200) code if request is successful.

## <span class="label label-info">POST</span> update location

Updates the current location (latitude and longitude) of a device. The location can be used for statistics or segmentation purposes.

### Request

**Path**

```bash
POST /apps/${app_id}/devices/${device_id}/report_statistics
```

**Headers**

```bash
Content-Type: application/json; charset: utf-8
```

**Required params**

The following attributes are required, wrapped in a `device` JSON object:

| param | description | range |
|-------|-------------|-------|
| latitude | The latitude attribute of the device location | -90 to 90 |
| longitude | The longitude attribute of the device location | -180 to 180 |

**Example request body**

```javascript
{
  "device": {
    "latitude": 4.111,
    "longitude": 10.111
  }
}
```

**Example request**

```bash
curl -X POST \
  -H "Content-Type: application/json; charset: utf-8" \
  -d '{ "device": {"latitude": 4.111, "longitude": 10.111} }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/report_statistics
```

## <span class="label label-info">POST</span> search device notifications

Makes a paginated search of the notifications received by a device. It allows filtering by notification tags.

### Request

**Path**

```bash
POST /apps/${app_id}/devices/${device_id}/search_notifications
```
**Headers**

 ```bash
 Content-Type: application/json; charset: utf-8
 ```

**Optional Params**

The request allows the inclusion of the following optional parameters:

| param | description | example |
|-------|-------------|---------|
| tags  | Returns notifications that contains all the given tags | `["alerts", "critical"]` |
| no_tags  | Returns notifications that does not contains any of the given tags | `["main_inbox"]` |

**Example request body**

```javascript
{
  "tags": ["moritaka","one"],
  "no_tags": ["two"]
}
```

**Example request**

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{ "tags": ["moritaka", "one"] }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices/1a2b3c4d5f/search_notifications
```

### Response

It returns a paginated array of notification objects:

**Example response**

```javascript
{
  "objects": [
    {
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
      "tags": [
        "tp_rich"
      ],
      "type": "Notification"
    }
  ]
}
```

## <span class="label label-info">POST</span> set custom property

Assign the value for the given custom property at the selected device.
Custom properties are useful to create segmented targets and to obtain statistics based on custom information.

### Request

**Path**

```bash
POST /apps/${app_id}/devices/:device_id/set_custom_property
```
**Headers**

 ```bash
 Content-Type: application/json; charset: utf-8
 ```

**Required params**

The following parameters are required:

| param | description |
|-------|-------------|
| name | name of the custom property to assign value to. If property does not exist, it will be created |
| type | type of the value of the property. Available types are described below |
| value | value to assign to the property. If null, property will be deleted from device

The available custom property types are:

| type | description | value example |
|------|-------------|---------------|
| string | A text as a sequence of characters | `"Male"`, `"New York"` |
| boolean | Logic data type with two possible values: true or false | `true`, `false` | 
| integer | A number without fractional component | `26`, `-6` |
| float | A number with fraction precision using floating point. The decimal separator is the '.' (dot) character. | `25.0`, `-1,999.95` |


**Example request body**

```javascript
{
  "name": "age",
  "type": "integer",
  "value": 43
}
```

**Example request**

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{ "name": "age", "type": "integer", "value": 43 }' \
  https://app.twinpush.com/api/v2/apps/623c8befd3f1b7f3/devices/923c8befd3f1b7f1/set_custom_property
```

### Response

It will return an OK (HTTP 200) code if request is successful.

## <span class="label label-important">DELETE</span> clear custom properties

Deletes all the custom property values associated with the given device.

### Request

**Path**

```bash
DELETE /apps/${app_id}/devices/${device_id}/clear_custom_properties
```

Deletes all the custom property values associated with the given device

__Example request__

```bash
curl -X DELETE \
  -H "Content-Type: application/json" \
  http://{{subdomain}}.twinpush.com/api/v2/apps/12mj18sja89/devices/1a2b3c4d5f/clear_custom_properties
```

### Response

It will return an OK (HTTP 200) code if request is successful.