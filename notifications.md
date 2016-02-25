# Notifications

##notifications - show GET

`https://{{subdomain}}.twinpush.com/api/{{version}}/devices/:device_id/notifications/:notification_id`

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/notifications/:notification_id`

Returns all the details of a notification.


__Example request__

```bash
curl -X GET \
https://{{subdomain}}.twinpush.com/api/{{version}}/devices/1a2b3c4d5f/notifications/2b3c4d5f6g
```


__Example response__

```javascript
{
    "objects": [
        {
            "id": "2b3c4d5f6g",
            "sound": "sound.aiff",
            "alert": "Test!",
            "badge": "4",
            "created_at": "2013-07-30 20:16:55 UTC",
            "updated_at": "2013-08-28 14:20:35 UTC",
            "last_sent_at": "2013-12-1 20:16:55 UTC",
            "custom_properties": { "callback": "cleanNotifications" },
            "type": "Notification",
            "device_id": "1a2b3c4d5f"
        }
    ],
    "references": []
}
```



##notifications - create POST

`https://{{subdomain}}.twinpush.com/api/{{version}}/apps/:app_id/notifications`

Creates a new notification with a date to be sent for some devices. All the devices must belong to the app specified in the uri with :app_id in the url.

This method requires an extra header parameter for security reasons. This header is <b>X-TwinPush-REST-API-Key-Creator</b> and can be found on the settings screen of an application.

__Parameters in the body__

<table class="table table-striped">
  <thead>
    <tr>
      <th>Name</th>
      <th>Mandatory</th>
      <th width="40%">Description</th>
      <th>Type</th>
      <th>Default Value</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>alert</td>
      <td>Yes</td>
      <td>The text it will be shown in the notification. It should be as descriptive as possible</td>
      <td>String</td>
      <td></td>
    </tr>
    <tr>
      <td>sound</td>
      <td>No</td>
      <td>The name of the file you should have as a resource in your application, and it's the one that will be played when a notification is received</td>
      <td>String</td>
      <td>"default"</td>
    </tr>

    <tr>
      <td>badge</td>
      <td>No</td>
      <td>The number you see in the icon of your app when you have unread notifications (only iOS)</td>
      <td>String / Number ("+1", "-1", 1)</td>
      <td>"+1"</td>
    </tr>
    <tr>
      <td>send_since</td>
      <td>No</td>
      <td>the time when you want to send the push (see the example for format).</td>
      <td>String (yyyy-mm-dd hh:mm:ss Z)</td>
      <td>Now</td>
    </tr>
    <tr>
      <td>tags</td>
      <td>No</td>
      <td>An array of strings to differentiate in the future this notification from others</td>
      <td>Array of Strings (["one", "two"])</td>
      <td>[]</td>
    </tr>
    <tr>
      <td>url</td>
      <td>No</td>
      <td>To send a rich notification you can set the url</td>
      <td>String ("`http://example.com`")</td>
      <td></td>
    </tr>

    <tr>
      <td>custom_properties</td>
      <td>No</td>
      <td>HashMap of custom properties useful for your application</td>
      <td>HashMap ("{"key1": "value1", "key2": "value2"}")</td>
      <td>{}</td>
    </tr>
  </tbody>
</table>


__Target (only one of these params)__

To devices ids:

```javascript
{
  "devices_ids": ["1a2b3c4d5f","2b3c4d5f6g","3c4d5f6g7h"]
}
```

Alternatively you can pass devices_alias with an array of aliases of devices instead of devices_ids.


```javascript
{
  "devices_aliases": ["techie5","lion","john"]
}
```

If you have segments you want to send the notification to, you can specify it in the request with the param segments, and an array of names of the segments you have previously saved in your app.

```javascript
{
  "segments": ["new_users","young_users"]
}
```


If you don't want to specify the receivers and send a broadcast notification (to all the devices in an app), you can do it with the broadcast parameter, be careful with this parameter.

```javascript
{
  "broadcast": true
}
```


__Examples__

__Example request (simple notification to an alias, send now)__

```bash
curl -X POST \
  -H "X-TwinPush-REST-API-Key-Creator: ${REST_API_TOKEN_CREATOR}" \
  -H "Content-Type: application/json" \
  -d '{
        "alert": "Test!",
        "devices_aliases": ["john"]
  }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/1a12b3c4d5f/notifications
```

__Response__

```javascript
{
  "objects": [
    {
      "id": "1a2b3c4d5f",
      "sound": "default",
      "alert": "Test!",
      "badge": "4",
      "send_since": "2013-10-03 15:14:33 +0000",
      "created_at": "2013-10-03 15:14:33 +0000",
      "updated_at": "2013-10-03 15:14:33 +0000",
      "type": "Notification"
    }
  ],
  "references": []
}
```

__Example request (rich notification to an alias, send in one week from now)__


```bash
curl -X POST \
  -H "X-TwinPush-REST-API-Key-Creator: ${REST_API_TOKEN_CREATOR}" \
  -H "Content-Type: application/json" \
  -d '{ "alert": "Test!",
      "send_since": "2013-10-10 15:14:33 +0000", 
      "url": "http://www.inception-explained.com/",
        "devices_aliases": ["john"]
      }' \
  https://{{subdomain}}.twinpush.com/api/{{version}}/apps/2b3c4d5f6g/notifications
```


__Response__

```javascript
{
  "objects": [
    {
      "id": "2b3c4d5f6g",
      "sound": "default",
      "alert": "Test!",
      "badge": "2",
      "created_at": "2013-07-30 20:16:55 UTC",
      "updated_at": "2013-08-28 14:20:35 UTC",
      "send_since": "2013-12-1 20:16:55 UTC",
      "url": "http://www.inception-explained.com/",
      "type": "Notification"
    }
  ],
  "references": []
}
```