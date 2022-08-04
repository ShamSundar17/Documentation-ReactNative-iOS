# **Installation of DR SDK**

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#installation-of-dr-sdk)
## Integration Overview 
![Screen Shot 2022-08-03 at 15 41 44](https://user-images.githubusercontent.com/95364508/182685046-3fa9dfed-070a-4423-aa2f-45b3bba09157.png)

### Step 1 : Extract

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-1--extract)

Extract the  `react-native-iu-library.zip`  file sahre by the DR Team to an easily accessible folder to integrate with your project.

### Step 2 : Open Terminal (Mac/Linux) or command prompt (Windows)

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-2--open-terminal-maclinux-or-command-prompt-windows)

Open the Command prompt (windows) / Terminal (Linux/Mac) and change directory to your project.

### Step 3: Add the React Native DR library

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-3-add-the-react-native-dr-library)

In command prompt / terminal type the following command.

yarn/node

```
npm  install  <extracted  folder>\react-native-iu-library  –save
yarn add <extracted folder>\react-native-iu-library –save
```

Path would be the "{Extracted folder}" where ReactNative-amlibrary.zip was extracted in Step 1

On successful completion of the add command you would be able to see a message similar to the following:

```
react-native-iu-library@1.0.0 added 1 package from 1 contributor and audited 1 package in 3.704s found 0 vulnerabilities

```

### Step 4.1 : Link library to project

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-4--link-library-to-project)

Run the following command to link the library to project

```
npx react-native link react-native-iu-library 

```

On successful completion of the command you would be able to see a message similar to the following

```
  -  info Linking "react-native-iu-library" iOS dependency 
    
  - info iOS module "react-native-iu-library" has been successfully linked 
    
  - info Linking "react-native-iu-library" Android dependency 
    
  - info Android module "react-native-iu-library" has been successfully linked 


```
### Step 5 : Pod Install

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-5--pod-install)

On your prompt / terminal navigate to ios folder of your project and type the following command

```
pod install

```
### Step 5.1 : Go to iOS Folder in react native project

Open projectName.xcworkspace file in Xcode

### Step 6: Add Local Config file

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-6-add-local-config-file)

DigitalReef SDK needs a local configuration file in the form of plist file.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>organization</key>
    <string>IU</string>
    <key>organizationId</key>
    <string>5a294f81993c8f1570c2550d</string>
    <key>fallbackURL</key>
    <string>https://sdk.digitalreef.com/v1/configs/remote</string>
    <key>timerTriggerConfig</key>
    <string>86400</string>
    <key>version</key>
    <string>1</string>
    <key>buildType</key>
    <string>SDK</string>
    <key>fcmProjectId</key>
    <string>iu-android-sdk</string>
    <key>fcmSenderId</key>
    <string>117519441630</string>
    <key>fbRemoteProjectId</key>
    <string>iu-android-sdk</string>
    <key>fbRemoteAPIKey</key>
    <string>AIzaSyAuiuXvkX3hbXTZv1q1KUh3PbvvTT2tb04</string>
    <key>fbRemoteAppId</key>
    <string>1:117519441630:android:7962cb3d01ff3cc2</string>
</dict>
</plist>

```

You would need to update the value of  **organization**  and  **organizationId**  in the above list.

Sample plist file looks as below:

![](https://files.readme.io/210c2fa-8ef4d9a-image1.png)

### Step 7: Add Permissions

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#step-7-add-permissions)

DR SDK needs few permissions which are listed below:

-   NSUserTrackingUsageDescription
-   UIBackgroundModes
    -   fetch
    -   remote-notification

![](https://files.readme.io/d0cb117-d85c033-image3.png)

Below image helps you configuring the Background mode

![](https://files.readme.io/70f0ef6-11a85f0-image4.gif)

## STEP 8: Add App Groups

[](https://developers.digitalreef.com/docs/integration-of-dr-ios-react-native-sdk#4-add-app-groups)

Add the following App Groups to

```
* Host Application's ```info.plist```
* Rich Notification service extension's ```Info.plist```

```

> ### ❗
> 
> App Group Data
> 
> App group's data should be same in both Host Application and Rich notification service extension.

```
<key>dbAppGroup</key>
<string>group.db.digitalreef.com</string>
<key>userDefaultsAppGroup</key>
<string>group.digitalreef.com</string>

```

Once added it would be similar to the image below

![](https://files.readme.io/e2c462c-fe2c7cf-image5.png)

> ### ❗
> 
> App Groups Naming
> 
> AppGroups string must be different for each host application otherwise there will be a shared database storage and shared user defaults storage between different apps.

 ### Step 9 : Enabling Rich Media and Push Buttons

Open projectName.xcworkspace file in Xcode.
As of iOS 10, it is possible to send attachments in the body of the push in the formats of images, gifs or videos 
and buttons. To enable this functionality it is necessary to create a Service Extension.

 File > New > Target and select Notification Service Extension
 	 ![image](https://user-images.githubusercontent.com/95364508/182460305-a1ee5087-67a5-4525-9d73-c190d4c09a41.png)
	 
 Make sure iOS version 12.0 or greater is selected for this Target

![Screen Shot 2022-08-02 at 16 48 17](https://user-images.githubusercontent.com/95364508/182460713-1ed26cb3-b8cf-4636-bb9a-5405fcaff6ec.png)

 On "Frameworks and Libraries" include the SDK and also make sure in option Embed, select "Do Not Embed"

![Screen Shot 2022-08-03 at 09 27 16](https://user-images.githubusercontent.com/95364508/182607426-2a7c3d3d-4317-4856-8293-db55ca6080d8.png)

In NotificationService.m file, include the call to the framework so that it presents the media in the notification:
   

    - (**void**)didReceiveNotificationRequest:(UNNotificationRequest *)request withContentHandler:(**void** (^)(UNNotificationContent * **_Nonnull**))contentHandler {
    
    **self**.contentHandler = contentHandler;
    
    **self**.bestAttemptContent = [request.content mutableCopy];
    
    [DigitalReef  includeMediaAttachmentWithRequest:request mutableContent:**self**.bestAttemptContent  contentHandler:**self**.contentHandler];
