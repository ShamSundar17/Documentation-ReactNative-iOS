# Opt-in/Opt-Out setting

### Monetization Opt-In / Opt-Out 
The host application can provide an option to the users to Opt-In and Opt-Out of the Monetization Ads services. The same can be accomplished via the following methods to access or update the Status.

### Update Opt-In Status

    DigitalReefSDK.optInToMonetizationAds(true);
    
The method accepts boolean value. When TRUE is passed, the user is Opted-In to the Ad services and when FALSE is passed, the user is Opted-Out of the Ad Service.

### Get Opt-in status

    DigitalReefSDK.getMonetizationAdOptInStatus();
    
The method returns boolean value. If TRUE is returned, the user has Opted-In to the Ad Services and when FALSE the user is Opted-Out of the Ad Services.

### Engagement Opt-In / Opt-Out :

The host application can provide an option to the users to Opt-In and Opt-Out of the Engagement Ads services. The same can be accomplished via the following methods to access or update the Status.

### Update Opt-In Status

    DigitalReefSDK.optInToEngagementAds(true);

The method accepts boolean value. When TRUE is passed, the user is Opted-In to the Ad services and when FALSE is passed, the user is Opted-Out of the Ad Service.

### Get Opt-In status

    DigitalReefSDK.getEngagementOptInStatusAds();
