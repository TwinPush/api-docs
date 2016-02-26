# API Concepts

Twinpush is a platform designed and built with the goal of making the process of sending push notifications to users really easy and intuitive. With that goal in mind, we offer a REST API that offers a wide functionality to be consumed through simple Web Service calls.

##What is REST?

It is a style of software architecture for distributed systems based on representations of resources and the manipulation of these resources through those representations.

##TwinPush Resources

TwinPush handle the following resources:

- **Application**: Is the first level of every API request. Represents a mobile application present in one or more platforms (iOS or Android).
- **Device**: Is the representation of a mobile device registered in an Application of the platform.
- **Notification**: A message created to be sent through a Push Notification to the devices of an Application. A notification is related to an application, but also with the devices to which it is targeted.

##RESTful routes

TwinPush offers the functionality through the API using RESTful routes that utlizes HTTP verbs to keep unique paths to a minimum, while making it easy to integrate and debug.

To access to a resource methods, URL must contain the correct path for the desired object:

| resource            | example path |
|---------------------|--------------|
| Application         | `/apps/:app_id/method` |
| Notification        | `/apps/:app_id/notifications/:notif_id/method` |
| Device              | `/apps/:app_id/devices/:device_id/method` |
| Device Notifications| `/apps/:app_id/devices/:device_id/notifications/:notif_id/method` |

## Input & Output Format

All API methods will return JSON objects as result and will expect JSON objects as body parameters in UTF-8 Character set.

For POST and PUT requests, it is required to include the following header:

```bash
Content-Type: application/json; charset=utf-8
```

## Pagination

In order to allow working with a big amount of records, TwinPush offers paginated results for every Web Service that returns a collection of objects.

| param       | description | default |
|-------------|-------------|---------|
| _per\_page_ | The number or results per page | 30 |
| _page_      | Current page. First page is 0. If 0 or negative value is given, page 1 will be returned | 1 |

Let's see an example

```bash
curl -X GET \
-H "X-TwinPush-REST-API-Token: ${REST_API_TOKEN}" \
-H "Content-Type: application/json" \
https://{{subdomain}}.twinpush.com/api/{{version}}/apps/1a2b3c4d5f/devices?page=1&amp;per_page=2
```

The response will be:

```javascript
{
  "offset": 0,
  "total_pages": 2,
  "total_entries": 4,
  "per_page": 2,
  "current_page": 1,
  "objects": [
    {
      "id": "2b3c4d5f6g",
      "alias_device": "techie4",
      "created_at": "2013-07-30 20:16:55 +0000",
      "updated_at": "2013-08-28 14:20:35 +0000",
      "last_registered_at": "2013-07-30 20:16:55 +0000",
      "app_id": "1a2b3c4d5f",
      "type": "Device"
    },
    {
      "id": "3c4d5f6g7h",
      "alias_device": "techie4",
      "created_at": "2013-07-30 20:16:55 +0000",
      "updated_at": "2013-08-28 14:20:35 +0000",
      "last_registered_at": "2013-07-30 20:16:55 +0000",
      "app_id": "1a2b3c4d5f",
      "type": "Device"
    }
  ],
  "references": [] 
}
```

In some cases, when a page without results is requested the answer will be the error NotFound, with the HTTP code 404.

**Note:** For clarity, the pagination options will be omitted in the rest of the documentation.

## HTTP Status Codes

For each request you make to the this API, we will return an HTTP status code. Following convention, the following status codes can be returned:

* <span class="label label-success">200</span> Success. The object was found, created, updated or deleted successfully.

* <span class="label label-warning">404</span> The object you're looking for doesn't exist.

* <span class="label label-warning">402</span> Not authorized to view this object.

* <span class="label label-warning">406</span> Not Acceptable (invalid format). You're probably sending wrong JSON or you need to specify the HTTP headers correctly.

* <span class="label label-warning">422</span> Unprocessable entity. Some of the given parameters is incorrect.

* <span class="label label-important">500</span> Server Error (hopefully not!). This means our server has some sort of problem while processing the request.
 
#Common error messages
When an error in a request occurred, in addition to the HTTP error code, the system will try to return a detailed error message to help the developer to debug its integration.
The details of the error will be returned as a JSON String in the response body with the following format:

```javascript
{
  "errors": {
    "type": "ErrorType"
    "message": "Detailed error message",
  }
}
```

The possible errors returned by the API Web Services are listed below:

| Code 	| Error Type             	| Description                                                                     
|------	|------------------------	|---------------------------------------------------------
| 403  	| InvalidToken           	| API Key Token is not valid or does not match with App ID
| 403  	| InvalidCreatorToken    	| Creator API Key Token is not valid or does not match with App ID
| 404  	| AppNotFound            	| Application not found for given application_id
| 404  	| DeviceNotFound         	| Device not found for given device_id
| 404  	| NotificationNotFound   	| Notification not found for given notification_id
| 404  	| DeliveryNotFound       	| Delivery not found for given notification and device
| 422  	| NotificationNotCreated 	| Some of the parameters given when trying to create a notification is not valid
| 422  	| DeviceNotCreated       	| Some of the parameters given when trying to register a device is not valid
| 422  	| DeviceNotUpdated       	| Some of the parameters given when trying to update a device info is not valid
| 422  	| InvalidProperty        	| The type or the value given when trying to assign a device property is not valid