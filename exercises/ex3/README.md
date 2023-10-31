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

13.  Toast message with confirming that configuration is saved will be shown
<br>![](/exercises/ex3/images/configuresaved.png)

14.	Click the "Replicate Order from SAP Order Management Foundation to SAP S4HANA" row and navigate to the Artifact Editor view.
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
<br>![](/exercises/ex3/images/22.png)

20.	Click on "Integrations and APIs" from the Monitor navigation item on the left pane. 
<br>![](/exercises/ex3/images/23.png)

21.	In the Overview page, from the listed Runtime, select the Runtime location where the artifact is deployed in Step 19
<br>![](/exercises/ex3/images/24.png)

22.	Click on tile "All" under "Manage Integration Content"
<br>![](/exercises/ex3/images/25.png)

23.	Verify that the Standard Content deployed in Step 19 is in Started state
<br>![](/exercises/ex3/images/26.png)

24.	Copy the generated endpoint
<br>![](/exercises/ex3/images/27.png)

25.	Open the Insomnia installed in your system, and paste the URL in the address and click Send. Wait for successful 200 response.
```url
https://az-slc.edge.integration.int.cloud.sap/http/s4onpremise/order
```
<br>![](/exercises/ex3/images/28.png)

26.	Go back to the Integration Suite UI and follow step 22 to step 23. 
Navigate to tile "All Artifacts" under "Monitor Message Processing"
<br>![](/exercises/ex3/images/29.png)

27.	A successful message processing entry will be shown
<br>![](/exercises/ex3/images/30.png)

## Summary

You've now completed the following:
1.  Able to discover an Standard Integration content.
2.  Deployed it on the Edge Integration Cell
3.  Established the connectivity to On-Premise S/4 HANA
4.  Iflow was executed successfully.

Continue to - [Exercise 4 - Excercise 4 ](../ex4/README.md)

