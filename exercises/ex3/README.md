# Discover, design and run pre-built standard integrations on Edge Integration Cell

In the previous exercise we have Activated and deployed an Edge Integration Cell, let's look at how we can Discover, design and run pre-built Standard Integrations on Edge Integration Cell. In this exercise we will use a pre-built standard content to connect to S/4 HANA backend system, trigger execution of the content deployed at Edge Integration Cell and perform operations like update of the S/4 HANA data objects.

##  Description

After completing these steps you will have deployed a Standard Integration on Edge Integration Cell and successfully executed it with On-Premise S/4 HANA system.

1. Navigate back to Home. In the Home page navigate to Capabilities and click on "Discover Integrations" under Build Integration Scenarios tile.
<br>![](/exercises/ex3/images/image.png)

2.  In the "Discover (Integrations)" view, navigate to the Search text box and enter the following package name: "SAP Order Management Foundation Integration with SAP S/4HANA" and click Enter. From the list of results, click on listed package "SAP Order Management Foundation Integration with SAP S/4HANA" 
<br>![](/exercises/ex3/images/3.png)

3.  In the package detail view, click on Copy button placed at top-right corner of the detail view
<br>![](/exercises/ex3/images/4.png)

4.  In the Messages pop-up, click on "Create copy" to create a named copy.
<br>![](/exercises/ex3/images/5.png)

5.  In the Provide suffix pop-up, enter the user Id that was provided with the tenant request. Clear the existing text which is shown as "14.10.2023.14.5.49" and enter userId e.g. userXXX and Click OK.
<br>![](/exercises/ex3/images/6.png)

6.  Upon confirmation, a Toast message "Package copied" will be shown. Click Close in the Messages pop-up 
<br>![](/exercises/ex3/images/7.png)

7.  Click Design from the sub navigation item in the left pane and click on "Integrations and APIs" and search the copied package (see the next step).
<br>![](/exercises/ex3/images/8.png)

9.  In the search box, type userXXX which you used as suffix during package copy operation. Package name with suffix as ".userXXX" be listed e.g. "SAP Order Management Foundation Integration with SAP S/4HANA.user130". 
Click the listed package and navigate to the Package details view.
<br>![](/exercises/ex3/images/9.png)

11.  Click on Artifacts tab, and select the check box for the following artifact "Replicate Order from SAP Order Management Foundation to SAP S4HANA"
<br>![](/exercises/ex3/images/10.png)

12.  Click on Actions, and click Configure from the sub menu item
<br>![](/exercises/ex3/images/11.png)

13.  In the "Configure Selected Artifacts" dialog, take time to look at various parameters in all 3 tabs - Sender, Receiver & More
<br>![](/exercises/ex3/images/12.png)

14.  Navigate to the Receiver tab and change the following parameter values:
```yaml
Address from http://<s4hana_hostname>/<s4hana_soap_endpoint> to https://proxyavrdev.hana.ondemand.com/Proxy/jenkslave55.cpi.c.eu-de-1.cloud.sap/9912/sap/bc/srt/scs_ext/sap/salesorderbulkrequest_in
Proxy Type from On-Premise to Internet
Credential Name from <s4hana credential> to <user will be provided during session>
```
After changing the values, click on "Save All"
<br>![](/exercises/ex3/images/13.png)

15.  Toast message with confirming that configuration is saved will be shown
<br>![](/exercises/ex3/images/14.png)

16.	Click the "Replicate Order from SAP Order Management Foundation to SAP S4HANA" row and navigate to the Artifact Editor view.
<br>![](/exercises/ex3/images/15.png)

17.	Look at the Artifact and validate whether required configurations are in place.
<br>![](/exercises/ex3/images/16.png)

18.	Click Deploy
<br>![](/exercises/ex3/images/17.png)

19.	Select Runtime Profile. Select one of the "Edge Integration Cell" runtime profile from the drop-down. And click Yes.
<br>![](/exercises/ex3/images/20.png)

20.	Click Ok on the Deployment dialog. 
<br>![](/exercises/ex3/images/21.png)

21.	Once the deployment is successful, a confirmation toast message will be shown
<br>![](/exercises/ex3/images/22.png)

22.	Click on "Integrations and APIs" from the Monitor navigation item on the left pane. 
<br>![](/exercises/ex3/images/23.png)

23.	In the Overview page, from the listed Runtime, select the Runtime location where the artifact is deployed in Step 19
<br>![](/exercises/ex3/images/24.png)

24.	Click on tile "All" under "Manage Integration Content"
<br>![](/exercises/ex3/images/25.png)

25.	Verify that the Standard Content deployed in Step 19 is in Started state
<br>![](/exercises/ex3/images/26.png)

27.	Copy the generated endpoint
<br>![](/exercises/ex3/images/27.png)

28.	Open the Insomnia installed in your system, and paste the URL in the address and click Send. Wait for successful 200 response.
```url
https://az-slc.edge.integration.int.cloud.sap/http/s4onpremise/order
```
<br>![](/exercises/ex3/images/28.png)

29.	Go back to the Integration Suite UI and follow step 22 to step 23. 
Navigate to tile "All Artifacts" under "Monitor Message Processing"
<br>![](/exercises/ex3/images/29.png)

30.	A successful message processing entry will be shown
<br>![](/exercises/ex3/images/30.png)

## Summary

You've now completed the following:
1.  Able to discover an Standard Integration content.
2.  Deployed it on the Edge Integration Cell
3.  Established the connectivity to On-Premise S/4 HANA
4.  Iflow was executed successfully.

Continue to - [Exercise 4 - Excercise 4 ](../ex4/README.md)

