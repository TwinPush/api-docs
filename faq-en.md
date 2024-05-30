# Frequently Asked Questions

## Devices / Users:
### New devices are not properly registering into the Platform

Sometimes you may experience that new devices are being check as inactive, you can confirm this in the "Devices" page at the Active column.

[![](https://i.imgur.com/qcmuH4Ll.png)](https://i.imgur.com/qcmuH4L.png)

This situation causes that all notifications will not be send to those devices. Most probably this is due to the limits of your license, find more information about [how licenses works here](#how-licenses-work). 



## Sending Notifications:

### What is the character limit for push messages?

Currently the limit on the size of the title or the alert for a push notification is 500 characters, but you have also to take consideration of the maximum size of the _payload_ (complete notification information) that is sent to Google and Apple services. This _payload_ includes all notification information, from title and alert, to custom properties or the rich content URL. And it has a total maximum size of 2KB for iOS and 4KB for Android. Each character usually occupies 1B, so it is difficult to reach this limit by making reasonable use. Even so, it is recommended to use short URLs as much as possible to push this limit further.

The maximum size of the text or title of a notification, therefore, would be more determined by what a phone or tablet screen may display (a notification that is too long could not be displayed full on the screen). These sizes are (approximately):

* **Title:** up to 40 characters
* **Text:** 40 characters with the screen locked and up to 200 in the iOS notification center and between 40 and 500 (if notifications with large text are used, which is the default TwinPush behavior) on Android

### Not receiving notifications

**Initial approach**

The first thing you have to do is to download the PDF report of the undelivered notification, you can find this report in the Push page, under details of that notification. 

[![](https://i.imgur.com/WXtySn1l.png)](https://i.imgur.com/WXtySn1.png)


You can see there, if there was an error that TwinPush could have identified. Most common errors are:

* **There are no deliveries:** There were no recipents (active devices) for your notification, from here, you should check if all devices of your recipient list are active, you can check that in "Devices" page at the Active column.

* **BadDeviceToken or No valid token or certificate error:** These kind of errors are common when sending notifications to iOS devices, and you must check your Apple APNS Certificate configuration at the settings section. Check for your Certificate expiring date or if you are using your Certificate correctly: Development or Production (Distribution checkbox checked) according to your current App, and apply corrections if needed.

[![](https://i.imgur.com/w1Yjmysl.png)](https://i.imgur.com/w1Yjmys.png)


In case the notification report is not showing any error, there might be some other reason, please check the following one by one:

* **Inactive Device:** mainly caused by a problem with the limit of your TwinPush license [here](#how-licenses-work).
* **Notifications not enabled in the device:** you should check if notifications are enabled for your App in that device and try again. When a user decides not to receive notifications from your App in his phone, the Push check will show uncheck in the Device list and he will not receive any notification, eventhough he could find them in his notification Mailbox, only if you have integrated this funtionality into your App.

[![](https://i.imgur.com/HniCiyDl.png)](https://i.imgur.com/HniCiyD.png)

* Connectivity problems with the device, sometimes a lack of coverage or a wifi connection into a corporative network can cause the notification not to arrive or to delay.
* The notification had arrived but it was unnoticed.

As a general rule, when you are not receiving notifications into a specific device, you should check the activity in your device: in the Devices page, find your device linked to your user name(Alias), and make sure it is effectively **active and has notifications enabled**. 

You could even reinstall your app and repeat the registering process.

If you have followed all these steps and still have a problem, please contact us at [support@twincoders.com](mailto:support@twincoders.com)


### Notifications are not seen in the App mailbox

TwinPush offers a notification mailbox per user, where a user can find all received notifications from the App.

In case you are not finding a specific notification into your mailbox, most probably you haven't mark that notification to get saved into the mailbox at the time you compose it. It is essential to mark the checkbox when composing the notification, in order to get it later in the mailbox.

### The notification text arrives incomplete

The length of notifications is limited by Apple and Google.

In that sense, you should be aware that you have a length limitation of a Push notification including all its parts: the text as well as the url, the custom properties, etc. Once a notification is composed, if that exceeds the limit, TwinPush will cut the text, to make sure it will be deliver to most devices.

For that reason you will see sometimes the text incomplete.

A way to improve your text completeness is by trying to shorten your URL by using URL shorteners or by reducing the size of your message.

### The Notification Web content cannot be seen

The notification arrives but the web content that should be seen when opening the notification is not doing so in the App.

If you are getting this error, there a a few verifications you should do:

* Check if the web content is properly loading into a web browser, sometimes this kind of problems are caused by an overload in the destination Web, due to huge amount of mobile users requesting it at the same time.
* The Web has not secure URL references. Some Mobile Operative Systems will not open a non secure destination Web into an App but will force to open it into the Device browser.

If you are not able to see any rich content received, you could probably have an integration problem with the Webview of the App, in that case contact to the developement team of your App.


### Troubles while uploading the target file

TwinPush offers you the posibility to upload a file containing the target users of your campaign.

The target file must comply a specific format and composition, you should follow this [guide to generate a target file](https://twincoders.atlassian.net/wiki/display/TWP/Import+target+file) for a proper operation.


## More Questions

### Not getting a confirmation or an invitation email

TwinPush sends you an email to confirm your email account when you register, when you request a new password, when you are invited to use an App or when other actions require it. Sometimes the email goes into your Spam folder or it can be block by the security system of your company. If you are not receiving an email, please do not hesitate to contact us at [support@twincoders.com](mailto:support@twincoders.com)


### No access to the settings of an App

Only the Account Administrator of an App has access to the settings of the App. The Administrator is the only one who has access to the Authentication Keys, can manage the team and the settings of the App.






## How Licenses Work

TwinPush has a license model based on the number of active devices.

An active device is the one that has been enrolled in the platform sometime by accessing through the App and has accessed at least once into an specific period of time. This period is 6 months by default, but this time parameter can be reconfigure on each account.

In this context, any device that has not registered any activity in a 6 months continuos period, it will become part of the inactive devices, so it will stop receiving notifications and reporting statistics and it will not count into the licensed devices.


### Out of license devices

In case that the number of active devices exceeds the number of licensed devices, TwinPush will mark the account as "out of license" and new enrolled devices will be marked as inactive. A new devices count is done every week.

In this way, active devices will be the ones that have registered activity in the last 6 months as well as the ones with older date of enrollment.

### Reconfiguring the time of activity

It is possible to reconfigure the time without activity needed to consider a device as inactive. This period of time (in months) can be adjusted by each account. In this way, is possible to force devices as inactive in a shorter time.

This parameter will allow an account to work always with the most active devices, but, on the other hand, that account will lose the ability to communicate with the least active ones, making impossible to carry out campaigns to reactivate these users.

if you want to change this value in your account, you should contact us at [support@twincoders.com](mailto:support@twincoders.com)


## Error Messages

The following table list describe the main error messages that return Google (FCM), Apple  (APNS) and Huawei (HMS) Push notification Platforms. TwinPush relay these messages in the response of Notification request. These messages could also be found in the downloadable report at a Notification view.

| Message | Description |
|---------|-------------|
| <strong>NotRegistered</strong><br/>Warning - FCM | An existing registration token may cease to be valid in a number of scenarios, including:<br>* If the client app unregisters with FCM.<br>* If the client app is automatically unregistered, which can happen if the user uninstalls the application. For example, on iOS, if the APNS Feedback Service reported the APNS token as invalid.<br>* If the registration token expires (for example, Google might decide to refresh registration tokens, or the APNS token has expired for iOS devices).<br>* If the client app is updated but the new version is not configured to receive messages.<br>For all these cases, remove this registration token from the app server and stop using it to send messages. |
| <strong>Unregistered</strong><br/>Warning - APNS | The device token is inactive for the specified topic. |
| <strong>MismatchSenderId</strong><br/>Error - FCM | A registration token is tied to a certain group of senders. When a client app registers for FCM, it must specify which senders are allowed to send messages. You should use one of those sender IDs when sending messages to the client app. If you switch to a different sender, the existing registration tokens won't work. |
| <strong>DeviceTokenNotForTopic</strong><br/>Error - APNS | The device token does not match the specified topic. |
| <strong>InvalidPackageName</strong><br/>Error - FCM | Make sure the message was addressed to a registration token whose package name matches the value passed in the request. |
| <strong>InvalidParameters</strong><br/>Error - FCM | Check that the provided parameters have the right name and type. |
| <strong>InvalidRegistration</strong><br/>Error - FCM | Check the format of the registration token you pass to the server. Make sure it matches the registration token the client app receives from registering with Firebase Notifications. Do not truncate or add additional characters. |
| <strong>CERTIFICATE\_EXPIRED</strong><br/>Error - APNS | OPENSSL\_internal:SSLV3\_ALERT\_CERTIFICATE_EXPIRED<br/> The APNS Certificate from Apple has already expired. |
| <strong>BadDeviceToken</strong><br/>Error - APNS | The specified device token was bad. Verify that the request contains a valid token and that the token matches the environment. |
| <strong>MissingRegistration</strong><br/>Error - FCM | Check that the request contains a registration token (in the registration\_id in a plain text message, or in the to or registration\_ids field in JSON). |
| <strong>80000000</strong><br/>Error - HMS | Success. No errors. |
| <strong>80100000</strong><br/>Error - HMS | Some tokens are successfully sent. Tokens identified by illegal token are those failed to be sent. Solution: Check these tokens in the return value. |
| <strong>80100001</strong><br/>Error - HMS | Some token parameters are incorrect. Solution: Check the token parameters as prompted in the response. |
| <strong>80100002</strong><br/>Error - HMS | The number of tokens must be 1 when a synchronization message is sent. Solution: Check the token field in the request. |
| <strong>80100003</strong><br/>Error - HMS | Incorrect message structure. Solution: Check the parameters in the message structure as prompted in the response. |
| <strong>80100004</strong><br/>Error - HMS | The message expiration time is earlier than the current time. Solution: Check the message field <strong>ttl.</strong> |
| <strong>80100013</strong><br/>Error - HMS | The <strong>collapse\_key</strong> message field is invalid. Solution: Check the message field <strong>collapse\_key</strong>. |
| <strong>80100016</strong><br/>Error - HMS | The message contains sensitive information. Solution: Check whether the message contains sensitive words. |
| <strong>80200001</strong><br/>Error - HMS | OAuth authentication error. Solution: The access token in the Authorization parameter in the request HTTP header failed to be authenticated. Ensure that the access token is correct. |
| <strong>80200003</strong><br/>Error - HMS | OAuth token expired. Solution: The access token in the Authorization parameter in the request HTTP header expired. Apply for a new access token. |
| <strong>80300002</strong><br/>Error - HMS | The current app does not have the permission to send push messages. Solution: Check the push message sending permission of the current app. |
| <strong>80300007</strong><br/>Error - HMS | All tokens are invalid. Solution: Check the token parameter. |
| <strong>80300008</strong><br/>Error - HMS | The message body size exceeds the default value. Solution: Reduce the message body size. |
| <strong>80300010</strong><br/>Error - HMS | The number of tokens in the message body exceeds the default value. Solution: Reduce the number of tokens and send them in batches. |
| <strong>81000001</strong><br/>Error - HMS | System internal error. Solution: Contact Huawei technical support of HUAWEI Push Kit. |


## Import target file

TwinPush offers the possibility to upload files to specify the target for a new notification.
Through this functionality, it is possible to send a notification to a group of users segmented outside the TwinPush platform.

The file must be an UTF8 plain text file (.txt or .csv) and contain only the accepted fields on each line.

### Simple targets

The most common way to create the target file is to create a plain text file (.txt of .csv) that contains only a single recipient identifier per line.

These recipient identifiers can be:

* **Device ID**: unique device identifier provided by TwinPush
* **Device Alias**: the alias assigned to the device on its registration

#### File examples

| alias              |
| :----------------- |
| alias1             |
| alias2             |
| alias3             |
| alias4             |


| device_id          |
| :----------------- |
| 2725b9d61a74e029   |
| f22ad2938a11d9f2   |
| 7723005d9ac27efb   |
| 682fcff66a3af683   |
| f8220f8f5acb83a9   |
| 3c2b4f94aa5c9660   |
| 6320b3352a14b019   |



### Multiple targets

It is possible to customize the information sent to every device or alias targeted in a notification.

This is done specifying a the target through a CSV file where every line represents is the target (device_id or alias) and the content is another hash of fields to override from the notification content parameters.

Through this method it is possible to customize the content fields of the notification received for every specified target:

* **title**: If defined, it will replace the title of the notification received by the target
* **alert**: If defined, it will replace the displayed notification message
* **url**: If defined, it will override the URL of the rich content
* **badge**: If defined, it will override the badge indicator of the main notification
* **custom_properties**: Properties defined by target will be merged with the notification properties overwriting when two keys collide. Will be defined as a JSON object.

If any of there parameters is not set, the message received by the user will contain the basic information defined in the main notification parameters.


| alias (mandatory),alert,title,url,custom properties,badge     |
| :------------------------------------------------------------ |
| alias1                                                        |
| alias2,New notification message                               |
| alias3,,New notification title                                |
| alias4,,,"http://new.notification.url"                        |
| alias5,,,,"{""new_custom_property"":true}"                    |
| alias6,,,,,"+1"                                               |
| alias7,New message,New title,"http://new.url","{""private"":true}","+1" |



| device_id (mandatory),alert,title,url,custom properties,badge |
| :------------------------------------------------------------ |
| 2725b9d61a74e029                                              |
| f22ad2938a11d9f2,New notification message                     |
| 7723005d9ac27efb,,New notification title                      |
| 682fcff66a3af683,,,"http://new.notification.url"              |
| f8220f8f5acb83a9,,,,"{""new_custom_property"":true}"          |
| 3c2b4f94aa5c9660,,,,,"+1"                                     |
| 6320b3352a14b019,New message,New title,"http://new.url","{""private"":true}","+1" |

