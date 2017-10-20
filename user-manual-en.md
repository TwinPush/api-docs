TwinPush User's Manual
===========================

**TwinPush** is Marketing Mobile Platform that allows sending Push notifications to Smartphones. TwinPush offers you a new Direct Communication Channel between your Business and your Users.

If If you have already built your own Mobile App by integrating our Android SDK or our iOS SDK, in your Android or iOS App respectively, you may start in this section. If you haven't yet, we can show you how to do it, in our Developers Section.

Sign up for a new TwinPush account at [app.twinpush.com](https://app.twinpush.com/), create a workspace for your App, upload your Google CGCM or your Apple APNS certificate and start sending Push notification. You can come back and check our User Manual anytime whenever you need help.

Troubles? please visit our FAQ Section and find answers or just Contact us, we will be happy to help you with TwinPush.


## Register and Login
If you don't have a user's account in Twinpush yet, you can register at [app.twinpush.com](https://app.twinpush.com/). Enterpise customers, may have its own subdomain to accesss: yourcompany.twinpush.com, please [contact us](mailto:info@twincoders.com) to get your own subdomain.

From this screen you will be able to:

1. **Register as a new user**: Create a new TwinPush account
2. **Create a new TwinPush account**:  Forgot password?
3. **Start session in TwinPush** using your login and password, if you have already registered.

[![](http://i.imgur.com/qzhBZ9Bl.png)](http://i.imgur.com/qzhBZ9B.png)


### Register
Write your email address and password. Remmeber that when you are register, you are agreeing with the [terms and conditions](http://app.twinpush.com/res/terms-of-service-es.pdf).

[![](http://i.imgur.com/bTWYU92l.png)](http://i.imgur.com/bTWYU92.png)



### Recover your password
Just write the email address you used when registering and in short time you will received an email with instructions to recover your password.


[![](http://i.imgur.com/oBKal8el.png)](http://i.imgur.com/oBKal8e.png)



## Apps
The first time you access to TwinPush, we will ask you to create your first App, by the moment we will only ask you your App Name and an Icon, just for your own reference. Later, you may modify these settings. When clicking to Creat App you wil be creating the workspace for your App.

* **App name**: try to give a name which describe your app. A good name will help to easy identify that app to you and to your collegues. Example: Customers Premium EU Android Production.
* **Icon**: It doesn't have to be the same icon that you use in the Market, it just allows you to quickly identify your app when you have many.

[![](http://i.imgur.com/jPDcJEbl.png)](http://i.imgur.com/jPDcJEb.png)




### Your First App
Now the workspace of your App is already created in TwinPush, you can see a Dashboard for your App. Next, you should integrate the TwinPush SDK into your mobile application and upload your certificate in order to send notifications. Follow the [SDK instructions here](http://www.twinpush.com/quickstart). 

[![](http://i.imgur.com/DTKxllIl.png)](http://i.imgur.com/DTKxllI.png)




### More Apps
Once you have created your first App, you can add more Apps at any time. If you want to add one more App and you are currently at the Dashboard of any App, click on the icon or name of your App in the upper bar and choose from the dropdown menu All applications. You will get a screen of all your Apps. By clicking down over the New Application icon you will be creating a new App. If you have two of more Apps already, you will get this screen as soon as you start session in TwinPush. Click over any App to get into the Dashboard of that App.

[![](http://i.imgur.com/Id54lKUl.png)](http://i.imgur.com/Id54lKU.png)




## Notifications
### Your First Notification
In order to send notifications, first, get access to the Dashboard of your App and click on the Push icon, on the left sidebar. If this is the first time you send a notification using this App, you will get the following screen. Click on Create the first one:

[![](http://i.imgur.com/q1oVzaOl.png)](http://i.imgur.com/q1oVzaO.png)


or you can also click on Create new notification on the upper right corner of the screen, just below your email address.

[![](http://i.imgur.com/OyqgsGol.png)](http://i.imgur.com/OyqgsGo.png)


If you have already sent notifications using this App, the Push icon will take you to the following screen. From here you can see statistics of your sent notifications, your groups of notifications, your last notifications, your campaigns, etc. You can also reuse groups, notifications or campaigns, we will explain you later how to do that. To create a new nottification from this screen, click on Create new notification on the upper right corner of the screen.

[![](http://i.imgur.com/YDpXFH9l.png)](http://i.imgur.com/YDpXFH9.png)



### Push Composer
By clicking on Create new notification you get into the Push Composer.


The Push Composer will show you as a series of tabs: Push, Content, Target, Schedule, Advanced and Summary and will take you by default to the first tab, Push.  The composer will also show you a phone simulation on the right side of the screen, where you see how your notification will show to the user when receive it from an Android or iOS device. 

To send a notification, the minimum required fields to complete are: the Alert, under the Push tab, and at least one Target, other options will help you to enhace your notifications, to perform different actions when the user clicks over the notification, to choose your target users or to schedule your notifications so you can send them whenever you want.

[![](http://i.imgur.com/ScVSXx6l.png)](http://i.imgur.com/ScVSXx6.png)


#### Push 
Use this tab to write your notification. The notification itselft is sent in plain text. When composing the message take into account that smartphones with outdated operative systems are limited to notifications size of arround 250 characters, in those 250 characters are included the plain text of the message and the rich text or URL, that you may want to add at the *Content* tab.

If you want your notifications reach most devices correctly, try to create concise messages and use URL shorteners whenever you can.

* **Tittle**: It's first line of the notification, it will show highlighted in the device.
* **Alert**: Write here the body of your message in plain text. 
* **Mailbox**: Mark this checkbox to make this notification get saved in the user's mailbox, in this way the user can review it whenever he wants.


[![](http://i.imgur.com/a1MCo4Vl.png)](http://i.imgur.com/a1MCo4V.png)



#### Content
At the Content tab, you will be able to select which additional action the notification will do when the user opens it up. In this way, you will be able to send to your users a rich text screen or an external URL, besides the notification. This function is very useful in marketing campaigns, where the notification message arouses the user's interest that could evolve into an immediat action.

* **None**: By choosing this option, when the user opens this notification, your App will open, in the same way as if he would open it up from your App icon.
* **URL**: Write here an URL with a landing page that will open in the smartphone when the user opens this notification.
* **HTML**: Create here a rich text HTML message, it can contain other external URL or image links, that will show to the user when he opens this notification.

[![](http://i.imgur.com/MlANILUl.png)](http://i.imgur.com/MlANILU.png)



#### Target tab
Use the Target tab to select the users you want them to receive this notification. You will be able to send this notification to all users of your App, to one or more users selected manually, to your segments, or you can also import a file with your own list of users or devices.

* **All**: By choosing All, the notification will be sent to all users registered in the platform and active at the time of sending this notitication.
* **User**: Here you can manually select one or more users or devices, to do that, you should identify a user by its Alias, or a device by its Device ID. Remember that any user has a unique Alias, but one user can own one or more devices. 
* **Segment**: Choose one or more segments here, you should have created first in the Target section. Just write the name of the segment one by one in the text box.
* **File**: Import a CSV (.csv) or a plain text (.txt) file with your own list of users or devices. You will be able to customize the message to send to each user or device. Find the rules for formatting the file [here](https://twincoders.atlassian.net/wiki/x/AgC7AQ).

[![](http://i.imgur.com/G6ePRXKl.png)](http://i.imgur.com/G6ePRXK.png)




#### Schedule
In the Schedule tab, you choose when your notification will be sent out. You can send it now or scheduled at a particular date/time. TwinPush also offers a powerful tool to program marketing campaigns under Setup campaign. Into a campaign you will be able to send a notification that you can repeat the number of times you set into a time period. You can set up this period of time to start and end at any time/date, or give a number of days, you can even set a range of hours or the days of the week. 

* **Now**: The notification will send as soon as you click on Send, that you will find when clicking Save & Preview button.
* **Schedule date**: The notification will be sent out at scheduled date and time set here.
* **Setup campaign**: You will send the same notification, a number of times into a time period. You can set the number of repetitions, and the time period. You may also limit the number of notifications that a device will received into a period of time.

[![](http://i.imgur.com/BuzqlUsl.png)](http://i.imgur.com/BuzqlUs.png)




#### Advanced
In the Advanced tab, you can tie this notification to a group, you can set the delivery speed and you can also interact with the application installed in the smartphone.

You can tie one or more notifications into a group, so you can create different groups according to your campaigns, seasons, products, targets, or whatever you want.

The delivery speed is very useful when you send massive notifications that contains actions to external links. It's possible that a peak of generated traffic impacts over the service availability of those external links, damaging the user's experience, as a consequence. TwinPush allow us to distribute along the time the delivery of a massive notification. 

Through TwinPush, we can interact with the App installed in the user's smartphone, we could set the Application Badge number, (the badge, is the number shown in the App icon), the ringtone that is played when a notification is received or the tag that identifies the type os notification received in the App, so you can set in you App to take different actions according to the Tag received.

* **Group name**: Add here this notification into a group or create a new group, just type a group name.
* **Delivery speed**: Choose the speed that a massive notification would be distributed along your users.
* **Badge**: Write here the badge that will show into the Smartphone, by default +1 will add one to the current number.
* **Sound**: Choose the ringtone that will play when this notification is received, use only in case your App was already set with a few ringtones.
* **Tags**: Send to your App in the Smartphone the type of notification you are sending, use only in case your App was already prepared to receive different types.

[![](http://i.imgur.com/mWeUQVyl.png)](http://i.imgur.com/mWeUQVy.png)



###Save & Preview

Once you have completed your notification, you can save it and then send it, by clicking on Save & Preview at the bottom right of the page. TwinPush will save your notification with all your settings and will show you a summary page in your screen. Check your notification and settings and if it's fine, send it with the button Send. If not, you can edit and correct it with the Edit button, or you can also Delete it. The Duplicate button is very useful to reuse notifications, you can create your own templates and make variations over an existing template.


[![](http://i.imgur.com/fgztUpsl.png)](http://i.imgur.com/fgztUps.png)






## Target
TwinPush includes a powerful tool to segment all users of your App. With this tool you will be able to create users' segments according to their location, according to the specifications of their device like brand, model or system version, according to their usage profile or even according to the user's information like his language or any other information that your App had captured from the user and had registered in the platform through the "Custom Properties", for example like his age, gender, occupation, interests or any other information. 



### Your First Target
In order to create targets, first, get access to your the Dashboard of your App and click on Target icon, on the left sidebar. If this is the first time you will create a target using this App, you will get the following screen. Click on Create target on center of the page: 

[![](http://i.imgur.com/Nb5JF8rl.png)](http://i.imgur.com/Nb5JF8r.png)

or you can also click on Create new target on the upper right corner of the screen, just below your email address.

[![](http://i.imgur.com/TcvMu9ul.png)](http://i.imgur.com/TcvMu9u.png)



If you have already created segments in your app, you will get the following screen. From here you will get a quick view of all your segments. For each segment is shown: the number of devices, the rate of target devices (green bar) over your total number of devices (grey background bar) and the type of filter applied to the segment: by location, by device properties or by usage statistics. To create a new segments from this screen, just click on Create new target on the upper right corner.

[![](http://i.imgur.com/aDJ3VmBl.png)](http://i.imgur.com/aDJ3VmB.png)




### Segments Editor
By clicking over Create a new target, you get into the Segments Editor. The Editor will take you to the Location filter by default. The Segments Editor is presented as a series of filters on the left margin of the page, you will progressively adding filters to your new segment. There are three type of filters: by Location, by User info or by Device info. In the middle of the page you will find configuration options for the selected filter. On the right side of the page you can add a condition to all selected filters and give a name to your brand new segment.

Each filter will show a small superscript to its relevant section when added. This superscript shows the total number of filters in that section. In this way, if you add 2 different languages, the superscript will show 2 in the language section, and if you add 3 different cities the superscript will show 3 in that section.

[![](http://i.imgur.com/sPiVl6Fl.png)](http://i.imgur.com/sPiVl6F.png)



#### Filters by Location
TwinPush offers different ways to filter a group of users according to their location: you can create one or more geofences, you can specify one or more countries, states, regions or cities, to do that click on Coordinates, Country, State, Region or City respectively.  

[![](http://i.imgur.com/EZD7ZPgl.png)](http://i.imgur.com/EZD7ZPg.png)



##### Creating Geofences
A geofence is a circular area determined by a geographic coordinate that identify the center of the circle and a radius given in meters.  To create a new geofence, click on Coordinates on the left to select that type of filter, then click on Add, on the upper right side of the map. You will get a window like the following screenshot. In this screen you should locate the map marker or POI to your desired position and select a radius by using the sliding bar in lower side. The selected area will show shaded in the map. On the upper side there is search box, you can write there the name of the city you want, you can also navigate the map with your mouse. Once your area of interest has been set, click on Add at the bottom right.

[![](http://i.imgur.com/mqySFNGl.png)](http://i.imgur.com/mqySFNG.png)



#### Filters by User info
In this section you will be able to segment your users according to the information that your app had gathered from the user. For that, your app should have register all this information in the TwinPush platform through the "Custom Properties", take a look how to do that [here](http://www.twinpush.com/documentation/devices#post-set-custom-property). By default TwinPush offers you language information of your users.

[![](http://i.imgur.com/OCQPf9Ql.png)](http://i.imgur.com/OCQPf9Q.png)


CBy setting up the "Custom Properties" you will be able to segment your users by: age, gender, occupation, interests or any other information that you want to add. To add a filter click on Other properties and then Add in the upper right, it will pop up a window like the following screenshot. In that, you can add a filter on any property that you will find in the dropdown menu.

[![](http://i.imgur.com/0mCoZg2l.png)](http://i.imgur.com/0mCoZg2.png)


#### Filters by Device Info

TwinPush provides you all the information gathered from the device from which your user access to your app. Information like: Platform (iOS or Android), Manufacturer, Model, System version, your App version, etc. You can segment your users by filtering them using that information.

[![](http://i.imgur.com/hDTE0mQl.png)](http://i.imgur.com/hDTE0mQ.png)




##### Usage statistics

TwinPush also allows you to segment your users according to the time they spend using your App. With this functionality you will be able to create campaigns to encourage the use of your App, you can reward your users with exclusive offers for that segment. To add a filter, click on Usage statistics and then Add in the upper right, it will pop up a window like the following screenshot. You can add filters on the total usage time, the inactivity period, the daily average usage time or the time lapsed from your app installation.

[![](http://i.imgur.com/SPZbFJdl.png)](http://i.imgur.com/SPZbFJd.png)



#### Summary
Once you have set up all your filters, you can add a final condition to all of them in the Summary section, at the right side of the screen. Remember that each filter set will be reflected into the superscript number next to its section. Select "Any" or "All"  from the dropdaown menu.

* **any**: your target will include all users that meet the conditions of any of the filters, for example: if you have created 2 filters by location, one in Madrid and another in Barcelona, by choosing *any*, your target will include all devices located in Madrid or in Barcelona, so both locations. The choice *any* gives you an wider target.
* **all**: your target will include all users that meet the conditions of all filters at the same time, for example: if you have created one filter by location in Madrid and another filter by platform iOS, by selecting *all*, your target will include all iOS users located in Madrid. The choice *all* gives you a narrower target.

Finally, you can give a name to your target and save it by clicking on Create Target.

[![](http://i.imgur.com/vOgDLhSl.png)](http://i.imgur.com/vOgDLhS.png)



## Audience / Users

TwinPush gives you the most relevat statistics from your users. Statistics are grouped in three blocks: Registered Users Data and Application usage, Users data and Devices data.
Go to the "[Devices](#devices)" view to get a more detailed information of your users and to export this data for an exhaustive study of this information.

### Registered User and Application usage:
**New registrations**: This chart shows new registrations within the latest 30 days.

**Platform**: The number of devices by platform: iOS or Android.

**Usage statistics**: This chart shows the usage time of your Application.

* Has used the application more than ...
* Has used the application less than ...
* Has used the app on average of more than ...
* Has used the app less than ...
* Has used the application from ...


[![](http://i.imgur.com/zvULR6gl.png)](http://i.imgur.com/zvULR6g.png)



### User Properties:
By integrating your App with the ["Custom Properties" in the SDK](http://developers.twinpush.com/quickstart), TwinPush is able to receive and show data related to the user properties, the following charts will automatically configure accordinf to the property type.

[![](http://i.imgur.com/QbrLVWcl.png)](http://i.imgur.com/QbrLVWc.png)



### Device Data:
The device data will also be shown throught the following charts:

* **Language** the one set in the device.
* **Manufacturer** of the device.

[![](http://i.imgur.com/LYs388ll.png)](http://i.imgur.com/LYs388l.png)



## Devices

In the Device screen, TwinPush allows you to see our entire database of Users. 


The view shows the devices with the most recent registered activity, as well as a search box, where you can search for a specific user by its Alias. The main table shows most relevant information of devices:

* **Push**: This field shows a tick when the user has approved receive Push notifications from your App.
* **Active**: This field shows a tick when a user is active (He has registered activity in your App at least one time in the last 6 months).
* **Alias**: It shows the alias name linked to the device.
* **Platform**: It shows an icon of the Operative System iOS or Android, as well as its version.
* **Device ID**: This is a TwinPush identifier of the device.
* **Registration date**: The date when the device registered to the platform for the first time.
* **Last opened**: The date when your App was open the last time.

[![](http://i.imgur.com/gePO5ojl.png)](http://i.imgur.com/gePO5oj.png)


By clicking on one device from the table, a popup window will open showing all the information related to that device. Besides the general information you will also see:

#### Device info:
* Manufacturer
* Model
* Device ID
* Operative System and version
* App version
* SDK version

#### Location info:
This functionality will work whenever you have integrate your App with [TwinPush SDK](http://developers.twinpush.com/quickstart) to get the geolocation active in the device. TwinPush will show you location information of the device.

* Country
* State
* City

#### User Data (Custom Properties):
The [TwinPush SDK](http://developers.twinpush.com/quickstart) allows you to register properties from the user in the Platform that will also be shown in the Devices screen.

[![](http://i.imgur.com/7s0LY7il.png)](http://i.imgur.com/7s0LY7i.png)


### Export data:
TwinPush allows you to Download all your user database at once thought a CVS file. This file will contain all information of each device.

According to the number of users registered in TwinPush this task could be heavy, so TwinPush gives you the posibility to download the latest autogenerated file or you can launch a new process to update this file.

[![](http://i.imgur.com/QddY7XDl.png)](http://i.imgur.com/QddY7XD.png)



## Settings

In the Settings screen you have access to the configuration parameter of your Application, the authentication keys used for the integration and to mage your own team.

### Application Details:
You can modify here basic information of your App, such as:

* **Name**: The name your App will show in TwinPush.
* **Time Zone**: You can set here the default time zone of your App, this parameter will affect the way that all time events are displayed to you, like notifications, scheduling and campaigns, but it will not take effect your notifications already scheduled. Please take note that on each campaigns you can also set a different time zone, unique for that campaign.
* **Icon**: Upload here an image that will identify your App in TwinPush.
* **Badge number**: This parameter sets the number displayed over the the icon of your App in iOS devices. This value is +1 by default.

[![](http://i.imgur.com/mInigYol.png)](http://i.imgur.com/mInigYo.png)



### Authentication Keys:

In this section you can set and check your authentication keys with the server, these keys are needed by the integration of your App with [TwinPush SDK](http://developers.twinpush.com/quickstart).

* **Sub-domain**: Here it's shown the subdomain we have to set in the integration with the SDK, it can be customized to Enterprise customers.
* **Application ID**: TwinPush identifier of you App.
* **API Key**: Authentication parameter for your App while connecting to TwinPush server.
* **API Key Creator**: Authentication parameter needed to create and send notifications from another server.


[![](http://i.imgur.com/gkkL1Fwl.png)](http://i.imgur.com/gkkL1Fw.png)


### Team Management:
TwinPush allows you to manage your own team to access to TwinPush platform. To invite a new member, as a guest, just write the new member's email address, TwinPush will send him or her an invitation email with instructions on how to get access to the platform.

Guest users have complete access to:

* Create and send Notifications.
* All users information.

Guest users have no access to:

* Settings, they cannot even see the API Keys or configure the APNS or GCM.
* Team Management.

The Administrator, the one who created the account, is the only one capable to add new members and to revoke access to any guest user.

[![](http://i.imgur.com/JKLo4unl.png)](http://i.imgur.com/JKLo4un.png)


### CGCM and APNS Settings:

In the Settings screen, TwinPush provides you access to configure [Apple APNS](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/Chapters/ApplePushService.html#//apple_ref/doc/uid/TP40008194-CH100-SW9/) and [Google GCM](https://developers.google.com/cloud-messaging/)services needed to send Push notifications to devices. These data should be provided by your App developer team, you can get more information about this configuration in the [SDK integration manual](http://developers.twinpush.com/quickstart).

TwinPush keeps track on the expiration date of your APNS certificate and will show you an alert when the time left to expire gets short avoiding you to get errors of not valid certificate when sending notifications to iOS devices.


[![](http://i.imgur.com/9nwWeDol.png)](http://i.imgur.com/9nwWeDo.png)



### Uploading a APNS Certificate:
While uploading the APNS certificate that Apple provides you, you should consider to set it as "Development" if you are compling and testing App versions in our platform, or "Production" if your App is already tested and ready for the Store.

[![](http://i.imgur.com/B9bIhgdl.png)](http://i.imgur.com/B9bIhgd.png)
