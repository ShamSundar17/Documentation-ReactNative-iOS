
# Invocation of SDK
To Invoke DR SDK from the Host App include the following lines of code.
 
 ### 1. Index.js File
    DigitalReefSDK.initiOS();

### 2. Push Notification Permission
DR SDK need to request Push Notification permission from the user to display the ad Notifications. Below is the sample code to invoke the same from any React component.

    DigitalReefSDK.requestPushPermission();

### 3. App Tracking Permission
DR SDK needs to request App Tracking permission from the user to collect IDFA details and track user activity on DR Platform. Below is the sample code to invoke the same from any React component.

    DigitalReefSDK.requestAppTrackingTransparencyPermission();
