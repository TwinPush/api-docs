# API Structure

All the important resources in TwinPush can be accesed by this API with simple requests using (index, new, edit show and delete actions).

# Understanding TwinPush Resources

In TwinPush your apps, notifications and devices are resources.
An app has an id, a name, a certificate, a password and an icon and can have many devices.
A device has a token and an alias and can have many notifications.
A notification has a sound, and alert message, a badge, some custom properties and a sent_at timestamp.

# A note about RESTful routes

Unless otherwise stated, most objects on the API conform to the following routes:

* <b>GET /collection</b> to list objects

* <b>GET /collection/id</b> to show an object

* <b>POST /collection</b> to create objects

* <b>PUT /collection/id</b> to update an object

* <b>DELETE /collection/id</b> to delete an object

# Format in API

All API methods accept JSON as input, and will return JSON. For each request, please specify the following headers:

<pre class="prettyprint lang-bash">
Accept: application/json
</pre>

# HTTP Status Codes

For each request you make to the this API, we will return an HTTP status
 code. Following convention, the following status codes can be returned:

* <span class="label label-success">200</span> Success. The object was found, created, updated or deleted successfully.

* <span class="label label-warning">404</span> The object you're looking for doesn't exist.

* <span class="label label-warning">402</span> Not authorized to view this object.

* <span class="label label-warning">406</span> Not Acceptable (invalid format). You're probably sending wrong JSON or you need to specify the HTTP headers correctly.

* <span class="label label-warning">422</span> Unprocessable entity. Some of the given parameters is incorrect.

* <span class="label label-important">500</span> Server Error (hopefully not!). This means our server has some sort of problem.

# Pagination

In order to provide paginated results we use a couple of parameters (both optionals):
<table cellspacing="5" cellpadding="5" border="0" style="text-align:left">
  <tbody>
  <tr>
    <th>per_page</th>
    <td>The number or results per page. If the value of <tt>per_page</tt> is 0, 30 will be the limit. Default: 30</td>
  </tr>
 
  <tr>
    <th>page</th>
    <td>The number of page. The first one is 1, not 0. If you pass 0 or a negative number the page number 1 will be returned. Default: 1</td>
  </tr>
</tbody></table>


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

**Note: The part of the pagination in the response will be removed in this documentation.**
 
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