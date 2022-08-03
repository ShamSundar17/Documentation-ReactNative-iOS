# Tracking In-App Events

DigitalReef SDK has potential to accept and track In-App Events from the host application, which can be used for tracking the User Journey and make many suggestive In-App message that can be configured and displayed to the user.

The SDK is preconfigured to track the following events by automatically:

-   1st Open of the Application
-   Application coming to foreground
-   Application going to background

### Sending events from Host application to SDK
Host Application can add any number of events to be tracked by the SDK.
Example for sending events :

    DigitalReefSDK.sendEventWithName('event_name');
