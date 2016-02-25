# SSL

All the requests will be done with SSL, so the URLs will be https://... instead of http://.

# Authentication

## Application ID

All the requests must identify the application by providing the Application ID as an URL parameter:
<pre class="prettyprint">https://app.twinpush.com/api/v2/apps/<strong>:app_id</strong>/...</pre>

The Application ID is a 16 alphanumeric characters string that can be obtained from the TwinPush console and that will be different for every registered application.

Examples of application ids are:

<pre class="prettyprint">cs555ab2356a37a0</pre>
<pre class="prettyprint">ab42d6512343133a</pre>

<br/>

## Additional authentication

In addition to Application ID, it is necessary an extra authentication parameter in every request. Depending on request type, this additional parameter method will vary:

- **Device ID:** Required for already registered devices
- **API Token:** Required for register and unregister requests
- **API Creator Token:** Required for requests that creates a notification


### Device ID

Request that are launched from already registered devices will authenticate by providing its `device_id`. If `device_id` and current application matches, access will be granted.

The Device ID is a 16 characters alphanumeric string that is provided from TwinPush when the device is registered.

It is set in every request as a request parameter:

<pre class="prettyprint">https://app.twinpush.com/api/v2/apps/:app_id/devices/<strong>:device_id</strong>...</pre>


### API Token

Required for **register** and **unregister** requests, it is a 32 alphanumeric characters string that can be obtained in the TwinPush web console.

These are examples of valid tokens:

<pre class="prettyprint">1c5cabc4055e03c64f123d9dbfb4d0e9</pre>
<pre class="prettyprint">ca044e0bc6a4f1cg23d9dbfb4251dhy6</pre>

The token will be passed as a header with `X-TwinPush-REST-API-Token` key, like in this example:

<pre class="prettyprint lang-bash">
curl -X GET \
-H "X-TwinPush-REST-API-Token: ${REST_API_TOKEN}" \
-H "Content-Type: application/json" \
https://app.twinpush.com/api/v2/....
</pre>


### API Creator token

With the same format than the *API Token*, the Creator Token is required for requests that creates a notification.

It is included as a header with `X-TwinPush-REST-API-Key-Creator`, like it is displayed in the following example:

<pre class="prettyprint lang-bash">
curl -X POST \
-H "X-TwinPush-REST-API-Key-Creator: ${REST_API_TOKEN_CREATOR}" \
-H "Content-Type: application/json" \
https://app.twinpush.com/api/v2/notifications
</pre>

<br/>