# Devices

Device model represent real devices, which means that there must be a correspondence with a user's device. Right now Android and iOS devices are supported.


##devices - register POST

`https://{{subdomain}}.twinpush.com/api/v2/apps/:app_id/devices/register`

Creates or updates the subscription or a device in the platform.

To launch this request it is needed to include the TwinPush Token in the `X-TwinPush-REST-API-Token` header.

__Input Parameters__

The register request accepts the following parameters:

- __udid__: an unique identifier of the device per application and platform. A good choice is the [ANDROID_ID](http://developer.android.com/reference/android/provider/Settings.Secure.html#ANDROID_ID) for Android and the [identifierForVendor](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIDevice_Class/index.html#//apple_ref/occ/instp/UIDevice/identifierForVendor) for iOS.
- __platform__: device platform. Available values are
  - "ios": for Apple iOS devices
  - "android": for Google Android devices
- __push_token__: the token provided for the device by the Push notification services (known as _registrationId_ for Android and _token_ for iOS). If the push token is not provided, the device will not receive push notifications, but it will be able to report usage statistics.
- __alias_device__: the alias is an __optional__ value to associate the device to a user of the client platform. Will be set to null if value is empty and will be ignored if not present in the request.

__Example request body__

```javascript
{
  "udid": "002ebf12a1255ddfa73967c3c5d20177",
  "platform": "ios",
  "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",
  "alias_device": "techie4"
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

__Example request__

```bash
curl -X POST \
  -H "X-TwinPush-REST-API-Token: ${REST_API_TOKEN}" \
  -H "Content-Type: application/json" \
  -d '{ "udid": "002ebf12a1255ddfa73967c3c5d20177", "platform": "ios", "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",  "alias_device": "techie4"}' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices
```

__Output__

The request will return an array of object that will only contain the created (or updated) device.

The `id` value of the device will be necessary to identify the device in subsequent requests.

__Example response__

```javascript
{
  "objects": [
    {
      "alias_device": "techie4",
      "app_id": "4d65532313a337a0",
      "created_at": "2014-11-07 17:05:40 UTC",
      "id": "a812cb78062ead53",
      "last_registered_at": "2014-11-07 17:05:40 UTC",
      "platform": "ios",
      "push_token": "5geamqy5 6xmrxfk1 5zpbcxmw ez3w7ksf cscpr55t trknkzap 7yyt41ss g6jrw7qz",
      "type": "Device",
      "updated_at": "2014-11-07 17:05:40 UTC"
    }
  ]
}
```


##devices - update badge POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/update_badge`

Updates the badge number of a device. The possible values are:

* A number, like 4, 5 or 900. The badge will be updated to that number.
* A plus sign and a number, like +1 or +400. The badge will be updated to the previous value plus the passed one.
* A minus sign and a number, like -1 or -400. The badge will be updated to the previous value minus the passed one.

If the new value is negative it will be set to 0.

__Example request__

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{ "badge": 12 }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/update_badge
```

##devices - open notification POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/notifications/:notification_id/open_notification`

The user opens a notification.

The open_at parameter should be a timestamp, if it is in another format an error code will be returned.

__Example request__

```bash
curl -X POST \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/notifications/1441befd34f112/open_notification
```

##devices - open app POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/open_app`

The user opens the app. This is useful to get statistics of use.

The open_at parameter should be a timestamp, if it is in another format an error code will be returned.

__Example request__

```bash
curl -X POST \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/open_app
```

##devices - close app POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/close_app`

The user closes the app. This is useful to get statistics of use.

The closed_at parameter should be a timestamp, if it is in another format an error code will be returned.

__Example request__

```bash
curl -X POST \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/close_app
```

##devices - report statistics POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/report_statistics`

Updated the statistics of a device. The following attributes are avaliable:

<table class="table table-striped">
  <thead>
    <tr>
      <th>Attribute</th>
      <th>Description</th>
      <th>Type</th>
      <th>Range</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Latitude</td>
      <td>The latitude attribute of the localization of the device</td>
      <td>Float</td>
      <td>-90 to 90</td>
    </tr>
    <tr>
      <td>Longitude</td>
      <td>The longitude attribute of the localization of the device</td>
      <td>Float</td>
      <td>-180 to 180</td>
    </tr>
  </tbody>
</table>

__Example request__

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{ "device": {"latitude": 4.111, "longitude": 10.111} }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/28be4fd32b731f3/report_statistics
```

##search notifications of a device - POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/search_notifications`

Search notifications with tags.

__Parameters you should pass:__

```javascript
{
  "tags": ["moritaka","one"],
  "no_tags": ["two"]
}
```

This will return all the notifications that have the tag __moritaka__ AND __one__ and don't have the tag __two__.

If tags and no_tags are not specified returns all the notifications.

__Example request__

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{ "tags": ["moritaka", "one"] }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices/1a2b3c4d5f/search_notifications
```

__Example response__
```javascript
{
  "objects": [
    {
      "id": "623c8befd3f1b7f3",
      "sound": "sound.aiff",
      "alert": "Test!",
      "badge": "4",
      "tags": [
        "moritaka",
        "one"
      ],
      "last_sent_at": "2013-12-1 20:16:55 UTC",
      "custom_properties": {
        "callback": "cleanNotifications",
        "rich_url": "http://www.inception-explained.com/"
      },
      "type": "Notification"
    }
  ],
  "references": []
}
```

##devices - destroy DELETE

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id`

Destroys an existing device.

To launch this request it is needed to include the TwinPush Token in the `X-TwinPush-REST-API-Token` header.

```bash
curl -X DELETE \
  -H "X-TwinPush-REST-API-Token: ${REST_API_TOKEN}" \
  -H "Content-Type: application/json" \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/12mj18sja89/devices/1a2b3c4d5f
```

##set custom property - POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/set_custom_property`

Assign the value for the given custom property at the selected device.

If a __null__ value is given, the custom property will be deleted from the device.

The available values for custom property type are:

<table class="table table-striped">
  <thead>
  <tr>
    <th>Value</th>
    <th>Description</th>
    <th>Value examples</th>
  </tr>
  </thead>

  <tbody>
  <tr>
    <td><i>string</i></td>
    <td>A text as a sequence of characters. On JSON, is usually represented surrounded by double quote character (")</td>
    <td><i>"Male"</i>, <i>"New York"</i></td>
  </tr>
  <tr>
    <td><i>boolean</i></td>
    <td>A logic data type with two possible values: true or false</td>
    <td><i>true</i>, <i>false</i></td>
  </tr>
  <tr>
    <td><i>integer</i></td>
    <td>A number without fractional component</td>
    <td><i>25</i>, <i>-6</i>, <i>10500</i></td>
  </tr>
  <tr>
    <td><i>float</i></td>
    <td>A number with fraction precision using floating point. The decimal separator is the '.' (dot) character.</td>
    <td><i>25.0</i>, <i>3.141592</i>, <i>-1,900.45</i></td>
  </tr>
  </tbody>
</table>

The given value for a custom property must match with property type.

__Example request__

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{ "name": "age", "type": "integer", "value": 43 }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/623c8befd3f1b7f3/devices/923c8befd3f1b7f1/set_custom_property
```

##clear custom properties - DELETE

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/devices/:device_id/clear_custom_properties`

Deletes all the custom property values associated with the given device

__Example request__

```bash
curl -X DELETE \
  -H "Content-Type: application/json" \
  http://{{subdomain}}.twinpush.com/api/v2/apps/12mj18sja89/devices/1a2b3c4d5f/clear_custom_properties
```