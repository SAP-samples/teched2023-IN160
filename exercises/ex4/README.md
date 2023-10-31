# Exercise 4: Design and run an API on Edge Integration Cell

In the concluding section of the tutorial, we will be focusing on the creation of an API, which serves as a consolidated entity enabling developers to incorporate both policies and steps. For this exercise, we will generate an API that directs to the same SAP S/4HANA REST endpoint URL employed in the prior exercise. Additionally, we will enhance its functionality by integrating traffic management features like Surge Protection and mediation capabilities such as the XML to JSON converter.

### Note

For all the subsequent steps in this exercise, please replace the xx in userxx with your respective id e.g user99

### Exercise steps

***

1. Navigate to the sub-navigation item - "Integrations and APIs" under the Design tab on the left side pane and click on "Create" to create a package

![](/exercises/ex4/images/04_01_0010.png)

2. Create a package with the details as shown in the image below and click on Save. Replace xx with the id assigned to you.

![](/exercises/ex4/images/04_02_0010.png)

3. Navigate to the Artifacts tab and add an API

![](/exercises/ex4/images/04_03_0010.png)

4. For the purpose of this exercise, we would be selecting the URL option

![](/exercises/ex4/images/04_04_0010.png)

5. Fill in the details for the API

    ```
    Name : Teched2023 API Artifact userxx
    URL: https://proxyavrdev.hana.ondemand.com/Proxy/jenkslave55.cpi.c.eu-de-1.cloud.sap/9912/sap/bc/srt/scs_ext/sap/salesorderbulkrequest_in
    API Base Path: /apiuserxx
    API State (select from dropdown) : Active
    API Version: 1.0.0
    Runtime Profile (select from dropdown): Edge Integration Cell - sap-teched-node
    ```

![](/exercises/ex4/images/04_05_0010.png)

6. Post the successful creation of the API, navigate into the "Overview" tab to confirm if the details are correct

![](/exercises/ex4/images/04_06_0010.png)

7. Click on Edit and navigate to the "Policies" tab and this is how the starter content should look like. As you can see the Authentication policy appears by default. Double click on the authentication policy and navigate to the property sheet at the bottom. By default Basic is not enabled and as an exercise, you should enable the Basic checkbox from the multi-select drop-down and click on Save

![](/exercises/ex4/images/04_07_01_0010.png)

![](/exercises/ex4/images/04_07_02_0010.png)

8. Click on the Authentication policy and you should see a pop-up with a set of actions. Click on the "+" icon

![](/exercises/ex4/images/04_08_0010.png)

9. Select the surge protection policy from the drop-down and add the Surge protection policy. The policy protects the target endpoint from a sudden spike in incoming requests. Navigate to the highlighted section below in the property sheet of the policy and fill in the details as shown in the UI. We are effectively configuring the policy to allow only 5 calls in a span of 10 seconds

![](/exercises/ex4/images/04_09_0010.png)

10. Click on Request Reply and when the pop-up opens, click on the "+" icon. Select "XML to JSON Converter" from the drop-down. Configure the step in accordance with the highlighted section shown in the UI and click on Save

![](/exercises/ex4/images/04_10_01_0010.png)

![](/exercises/ex4/images/04_10_02_0010.png)

11. Now we are ready to deploy the API on Edge. Click on "..." icon on the top right corner and from the dropdown select "Deploy". During creation we had already configured the runtime profile and the hence this would deploy the API to the configured edge runtime profile

![](/exercises/ex4/images/04_11_0010.png)

12. Post a successful deployment , the status field for the API should change from "Not deployed" to the corresponding state. In the UI, the highlighted section shows that the API is successfully deployed and is ready for execution

![](/exercises/ex4/images/04_12_0010.png)

13. Navigate out of the edit view by selecting "Cancel" from the dropdown as shown

![](/exercises/ex4/images/04_13_0010.png)

14. Now we would navigate to the monitoring shell navigation item on the left and select "Integrations and API". Post the selection , we would select the edge runtime profile from the dropdown.

![](/exercises/ex4/images/04_14_0010.png)

15. Under the Manage Integration Content section , click on the highlighted tile to navigate to the list view of all the deployed artifacts

![](/exercises/ex4/images/04_15_0010.png)

16. Select the artifact "Teched2023 API Artifact userxx" and you should see the endpoint which would be used to access the API. Click on the highlighted icon and this copy the deployed url to the clipboard. From the dropdown below , change the log level to "Debug" as shown below. Confirm the change on the dialog box which appears post the log level is changed from the dropdown.

<br>![](/exercises/ex4/images/04_16_0010.png)
<br>![](/exercises/ex4/images/04_17_0010.png)
<br>![](/exercises/ex4/images/04_18_0010.png)

17. Now that we have successfully deployed the API , it is time to test the API. Create a new request in the insomnia client in a similar fashion as mentioned in the [previous exercise](../ex3/README.md). In the url section , paste the url which was already copied to clipboard as part of the previous step.
<br>
Add the following credentials

    
        USERNAME = sb-93d61073-f8ba-4faa-98e0-89fd3a424277!b2246|it-rt-iat-prism-std!b144
        PASSWORD = 174ebb0d-4e0f-43dd-994a-58629ec524bf$mPrfigEVYsOs71X2jfWBkBB7e24Mi8M94xkCuREs1Yo=
    

![](/exercises/ex4/images/04_19_0010.png)

18. Post a successful request, we would try to simulate the scenario, where we violate the criteria for surge protection policy. Execute the request on the insomnia client by clicking on the "Send" button repeatedly such that we end up executing more than 5 requests in a span of 10 seconds. Ideally, on making the 6th request, the surge protection policy should get triggered and you should see a response as shown in the UI. 

![](/exercises/ex4/images/04_20_0010.png)

19. Now , we would navigate back to the monitoring UI to visualize the execution flow. Click on Monitor Message Processing link as shown in the UI for the artifact artifact "Teched2023 API Artifact userxx" and this should show all the executions of the API with the latest execution appearing right at the top

![](/exercises/ex4/images/04_21_0010.png)

20. Select the latest execution entry click on the Debug link as shown below

![](/exercises/ex4/images/04_22_0010.png)

21. We can see that the failure happened at the Surge protection policy and on clicking the "x" icon , we can see the actual error in the toast message

<br>![](/exercises/ex4/images/04_23_0010.png)
<br>![](/exercises/ex4/images/04_24_0010.png)

## Summary

You've now completed the following:

1. Able to model an API
2. Deployed it on the Edge Integration Cell
3. Execute the API and violate the surge protection policy successfully which prevents the backend from traffic surges
4. Monitor the execution flow of the API 
