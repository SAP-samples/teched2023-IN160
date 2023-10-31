# Discover, design and run pre-built standard integration on Edge Integration Cell

In the previous exercise, we have activated and deployed Edge Integration Cell runtime. Now let's look at how we can discover, design and run pre-built standard integrations on Edge Integration Cell. In this exercise, we will use a pre-built standard content to connect to SAP S/4HANA backend system, trigger execution of the content deployed on Edge Integration Cell and perform operations like update of the S/4HANA data objects.

##  Description

After completing these steps you will have deployed a standard integration on Edge Integration Cell and successfully executed it with on-premise SAP S/4HANA system.

1. Navigate back to Home. In the Home page navigate to Capabilities and click on "Discover Integrations" under Build Integration Scenarios tile.
<br>![](/exercises/ex3/images/image.png)

2.  In the "Discover (Integrations)" view, navigate to the Search text box and enter the following package name: "SAP Order Management Foundation Integration with SAP S/4HANA" and click Enter. From the list of results, click on listed package "SAP Order Management Foundation Integration with SAP S/4HANA" 
<br>![](/exercises/ex3/images/package%20search.png)

3.  In the package detail view, click on Copy button placed at top-right corner of the detail view
<br>![](/exercises/ex3/images/4.png)

4.  In the Messages pop-up, click on "Create copy" to create a named copy.
<br>![](/exercises/ex3/images/5.png)

5.  In the Provide suffix pop-up, enter the username that was provided to you. Clear the existing text which is shown as "14.10.2023.14.5.49" and enter username e.g. userXX and Click OK.
<br>![](/exercises/ex3/images/6.png)

6.  Upon confirmation, a toast message "Package copied" will be shown. Click Close in the messages pop-up 
<br>![](/exercises/ex3/images/7.png)

7.  Click Design from the sub navigation item in the left pane and click on "Integrations and APIs" and search the copied package (see the next step).
<br>![](/exercises/ex3/images/8.png)

8.  In the search box, type userXX which you used as suffix during package copy operation. Package name with suffix as ".userXX" be listed e.g. "SAP Order Management Foundation Integration with SAP S/4HANA.user130". 
Click the listed package and navigate to the Package details view.
<br>![](/exercises/ex3/images/9.png)

9.  Click on Artifacts tab, and select the check box for the following artifact "Replicate Order from SAP Order Management Foundation to SAP S4HANA"
<br>![](/exercises/ex3/images/10.png)

10.  Click on Actions, and click Configure from the sub menu item
<br>![](/exercises/ex3/images/11.png)

11.  In the "Configure Selected Artifacts" dialog, and change the following parameter under Sender tab under Connection section. Suffix the address with the "_userXX" this is the same user which you chose during the onboarding.
```yaml
Address = /s4onpremise/order_userXX
```
<br>![](/exercises/ex3/images/changesenderaddress.png)

12.  Navigate to the Receiver tab and change the following parameter values:
```yaml
In the "Address" field enter, https://proxyavrdev.hana.ondemand.com/Proxy/jenkslave55.cpi.c.eu-de-1.cloud.sap/9912/sap/bc/srt/scs_ext/sap/salesorderbulkrequest_in
In the "Proxy Type" field choose, Internet
and for "Authentication", choose None
```
After changing the values, click on "Save All"
<br>![](/exercises/ex3/images/configureiflow.png)

13.  Toast message with confirming that configuration is saved will be shown. Click Cancel to close the Configure dialog.
<br>![](/exercises/ex3/images/configuresaved.png)

14.	Click the Standard Content "Replicate Order from SAP Order Management Foundation to SAP S4HANA" row and navigate to the Artifact Editor view.
<br>![](/exercises/ex3/images/15.png)

15.	Look at the Artifact and validate whether required configurations are in place.
<br>![](/exercises/ex3/images/16.png)

16.	Click Deploy
<br>![](/exercises/ex3/images/deployclick.png)

17.	Select Runtime Profile. Select one of the "Edge Integration Cell" runtime profile from the drop-down. And click Yes.
<br>![](/exercises/ex3/images/deploy.png)

18.	Click Ok on the Deployment dialog. 
<br>![](/exercises/ex3/images/21.png)

19.	Once the deployment is successful, a confirmation toast message will be shown
<br>![](/exercises/ex3/images/deployedsuccess.png)

20.	Click on "Integrations and APIs" from the Monitor navigation item on the left pane. 
<br>![](/exercises/ex3/images/navigatetomonitorview.png)

21.	In the Overview page, from the listed Runtime, select the Runtime location where the artifact is deployed in Step 19
<br>![](/exercises/ex3/images/chooseedgeinmonitoring.png)

22.	Click on tile "All" under "Manage Integration Content"
<br>![](/exercises/ex3/images/tileselect.png)

23.	Verify that the Standard Content deployed in Step 19 is in Started state. Check the details like ID; it should be suffixed with userXX used during onboarding.
<br>![](/exercises/ex3/images/iflowstarted.png)

24.	Copy the generated endpoint. In this case example URL is below (DO NOT COPY THIS URL)
```url
https://eic-teched2023-demo.sapintegrationsuite.de/http/s4onpremise/order_user130
```
<br>![](/exercises/ex3/images/copyendpoint.png)

25.	Open the Insomnia installed in your system
    
26.	Use "Scratch Pad" option when prompted to login
<br>![](/exercises/ex3/images/insomniascratchpad.png)

27. Create a new HTTP Request by clicking on '+' sign
<br>![](/exercises/ex3/images/insomnianewrequest.png)

28. Change the Request method from 'GET' to 'POST' and Paste the URL copied in Step 24 in the URL box
<br>![](/exercises/ex3/images/insomnianewpostrequest.png)

29. Set the payload. In the 'Body' tab, select JSON to add the JSON payload.
<br>![](/exercises/ex3/images/insomniasetbody.png)

30. Add the following payload in the body text area

```json
{
  "id": "dc3ea1c1-b4fb-4fa0-a83f-c6ae843b879c",
  "version": 1,
  "orderNumber": 456789,
  "precedingDocument": null,
  "metadata": {
    "createdAt": "2020-03-27T17:16:52.968Z",
    "createdBy": null,
    "changedAt": "2020-03-27T15:16:52.968Z",
    "changedBy": null
  },
  "owner": "ruth@domain.com",
  "market": {
    "marketId": "A1",
    "marketName": "US East",
    "currency": "EUR",
    "salesArea": {
      "salesOrganization": "1710",
      "distributionChannel": "10",
      "division": "00"
    }
  },
  "timeZone": "America/New_York",
  "paymentData": [
    {
      "method": "Card",
      "paymentCardToken": "as324dad333dddas22415ga"
    }
  ],
  "customer": {
    "customerNumber": "17100009",
    "addresses": [
      {
        "street": "Billing Street",
        "houseNumber": "1196",
        "building": "buildBill-1",
        "roomNumber": "11",
        "floorNumber": "1",
        "postalCode": "H1A 1H6",
        "city": "Montreal",
        "country": "CA",
        "district": "bill2-district",
        "state": "QC",
        "phone": "5141112233",
        "email": "Bill@Samplecustomer.Com",
        "fax": "5141113344",
        "additionalAddressInfo": null,
        "correspondenceLanguage": "Fr",
        "addressType": "BILL_TO",
        "person": {
          "firstName": "Bill",
          "middleName": "MiddleBill",
          "lastName": "LastNameBill",
          "academicTitle": "Ms"
        },
        "pOBox": "1100"
      },
      {
        "street": "Shipping Street",
        "houseNumber": "2242",
        "building": "ship-2",
        "roomNumber": "22",
        "floorNumber": "2",
        "postalCode": "24152",
        "city": "Chicago",
        "country": "US",
        "district": "ship2-district",
        "state": "IL",
        "phone": "2122223344",
        "email": "Ship2@Samplecustomer.Com",
        "fax": "2122224455",
        "additionalAddressInfo": "test notes ship",
        "correspondenceLanguage": "En",
        "addressType": "SHIP_TO",
        "person": {
          "firstName": "Shipster",
          "middleName": "MiddleShip",
          "lastName": "LastNameShip",
          "academicTitle": "Mr"
        },
        "pOBox": "abc"
      }
    ]
  },
  "description": "ruth's order",
  "status": "RELEASED",
  "priceType": "Net",
  "customReferences": [],
  "orderItems": [
    {
      "id": "4cd1629a-85be-41b4-b379-656288f25b21",
      "lineNumber": "1",
      "itemType": "physicalItem",
      "quantity": {
        "value": 3,
        "unit": "PCE"
      },
      "product": {
        "id": "e0981039-8298-464e-a8f0-32be92a8ba32",
        "sourceSystemReference": {
          "sourceSystemProductId": "TG11"
        }
      },
      "customReferences": [],
      "price": {
        "aspectsData": {
          "physicalItemPrice": {
            "priceTotals": [
              {
                "priceCategory": "onetime",
                "finalAmount": 40.68
              }
            ]
          }
        }
      },
      "aspectsData": {
        "physicalItem": {
          "scheduleLines": [
            {
              "deliverySource": {
                "sourceId": "1710",
                "sourceType": "STORE",
                "sourceName": "Downtown"
              },
              "availableFrom": "2020-03-28T19:16:52.968Z",
              "quantity": {
                "unit": "PCE",
                "value": 3
              }
            }
          ]
        }
      }
    }
  ]
}
```
<br>![](/exercises/ex3/images/insomniabodypayload.png)

31. Navigate to 'Auth' tab and select 'Basic Auth'
<br>![](/exercises/ex3/images/insomniasetbasicauth.png)

32.	Add the following credentials
    - USERNAME = sb-93d61073-f8ba-4faa-98e0-89fd3a424277!b2246|it-rt-iat-prism-std!b144
    - PASSWORD = 174ebb0d-4e0f-43dd-994a-58629ec524bf$mPrfigEVYsOs71X2jfWBkBB7e24Mi8M94xkCuREs1Yo=
<br>![](/exercises/ex3/images/insomniabasicauthset.png)

33.	Trigger the Endpoint - click on 'Send'. Upon success, you will receive '200 OK' status as a response. Copy the "message ID" from the response 'message'
<br>![](/exercises/ex3/images/insomniasuccessfulpost.png)

34. Switch back to the Integration Suite UI. Click on "Integrations and APIs" from the Monitor navigation item on the left pane 
<br>![](/exercises/ex3/images/navigatebacktoISUITE.png)

35. Navigate to tile "All Artifacts" under "Monitor Message Processing"
<br>![](/exercises/ex3/images/mpltile.png)

36.	A successful message processing entry will be shown against the copied "Message ID". Input the "message ID" copied in Step 33 in the ID search box.
<br>![](/exercises/ex3/images/mplsuccess.png)

## Summary

You've now completed the following:
1.  Able to discover an Standard Integration content.
2.  Deployed it on the Edge Integration Cell
3.  Established the connectivity to On-Premise S/4 HANA
4.  Iflow was executed successfully.

Continue to - [Exercise 4 - Excercise 4 ](../ex4/README.md)

