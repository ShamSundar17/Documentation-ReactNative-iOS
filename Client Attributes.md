
# Client Attributes

In some cases, the Host application may need to pass attributes to the DR SDK. This is supported with the  _ClientAttributes_  class provided as a part of the SDK.

The following are the keys which we have pre-defied.

-   Phone number - "PHONE_NUMBER"
-   Carrier - "CARRIER"
-   Bill type - "BILL_TYPE" // POSTPAY or PREPAY.

In addition to the keys above you are free to add your own keys, DR would be storing the information in DB for future reference.

The following code snippet shows how this can be done.

    var jsonObject = {
	    'BILL_TYPE':  'POSTPAY',
	    'CARRIER':  'TIM-BRASIL',    
	    'PHONE_NUMBER':  '1122334455'
    }; 
	    DigitalReefSDK.setClientAttributes(jsonObject)
    }};
## 

**External ID**

[](https://developers.digitalreef.com/docs/client-attributes-4#external-id)

We can set the Partner ID or External ID or Host App reference ID using the Client Attributes.

For this we have reserved a KEY as  **"EXTERNAL_ID"**.

Example:

    var jsonObject = {
	    'EXTERNAL_ID':  'john.doe@example.com'
    }; 
	    DigitalReefSDK.setClientAttributes(jsonObject)
    }};
