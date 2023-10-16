# Exercise 4: Design and run an API on Edge Integration Cell

In the final part of the tutorial, we will create an API, which is a unified entity that allows the API Developer to add policies as well as steps. For the purpose of this exercise, we would be creating an API using the REST endpoint URL with traffic management capabilities like Surge Protection and Quota, along with mediation capabilities in the form of a content modifier.

### Exercise steps

***

1. Navigate to the sub-navigation item - Integrations and APIs under the Design tab and click on Create to create a package
   
<br>![](/exercises/ex4/images/04_01_0010.png)

2. Create a package with the details as shown in the image below and click on Save
   
<br>![](/exercises/ex4/images/04_02_0010.png)

3. Navigate to the Artifacts tab and add an API
   
<br>![](/exercises/ex4/images/04_03_0010.png)  

4. For the purpose of this exercise, we would be selecting the URL option

 <br>![](/exercises/ex4/images/04_04_0010.png)

5. Fill in the details for the API as shown below

<br>![](/exercises/ex4/images/04_05_0010.png)

6. Post the successful creation of the API, navigate into the overview tab to confirm if the details are correct

 <br>![](/exercises/ex4/images/04_06_0010.png) 

 7. Click on Edit and navigate to the policy tab and this is how the starter content should look like. As you can see the Authentication policy appears by default. Double click on the authentication policy and navigate to the property sheet at the bottom. By default Basic is not enabled and as an exercise, you should enable the Basic checkbox from the multi-select drop-down and click on Save
 
 <br>![](/exercises/ex4/images/04_07_0010.png) 

 8. Click on the Authentication policy and you should see a pop-up with a set of actions. Click on the "+" icon

 <br>![](/exercises/ex4/images/04_08_0010.png) 

 9. Select the surge protection policy from the drop-down and add the Surge protection policy. The policy protects the target endpoint from a sudden spike in incoming requests

<br>![](/exercises/ex4/images/04_09_0010.png) 

10. Navigate the surge protection policy and add the required details in respective property sheet. The current configuration allows 5 calls over a span of 10 seconds
    
<br>![](/exercises/ex4/images/04_10_0010.png) 

11. Click on the Surge Protection policy and you should see a pop-up with a set of actions. Click on the "+" icon and select Quota Policy. Double click on the quota policy and select the "Fixed" option from the dropdown

<br>![](/exercises/ex4/images/04_11_0010.png)  

12. Select the convenient time in the past from the Start Time (UTC) option using the control which pops up. Please note that the timestamp is in UTC. For the sake of this exercise , we have selected 12th October 11:00:00 (UTC) as the timestamp

<br>![](/exercises/ex4/images/04_12_0010.png)

13. Fill in the remaining fields in the Quota Policy property sheet and click on Save. For the purpose of this exercise, we are allowing 12 calls in a span of 30 seconds for any client which tries to access the API. The field "Quota Identifier" should uniquely identify the client against which the quota is assigned. As part of the highlighted configuration ,it expects "clientkey" header as part of the incoming request to contain the value of the client identifier. Failing to pass this header in the incoming request should fail the policy and hence the request, that is in accordance with the "On Error" configuration which is configured to "Abort" the request if the policy fails. We would verify this during the testing of the API

<br>![](/exercises/ex4/images/04_13_0010.png)

14. Click on Quota policy and when the pop up opens, click on the "+" icon. Select the Content Modifier step under the Transfomration section

<br>![](/exercises/ex4/images/04_13_0010.png)

15. Navigate to the property sheet of the content modifier and under the Message Header subtab add a custom header as shown in the image below. Click on Save

<br>![](/exercises/ex4/images/04_14_0010.png)

16. Now click on Deploy and this shall trigger the deployment of the content to the configured runtime edge location 

<br>![](/exercises/ex4/images/04_15_0010.png)

17. Navigate to the monitoring tab and select the appropriate runtime location from the dropdown where the content is deployed

<br>![](/exercises/ex4/images/04_16_0010.png)

18. Click on Manage Integration Content and confirm that the deployed artifact is in a "Started" state and the API is deployed successfully

<br>![](/exercises/ex4/images/04_17_0010.png)

19. From the dropdown, we would select Debug as the log level such that later on post execution of the API , we can visualize the execution of policies and steps in the deployed artifact

<br>![](/exercises/ex4/images/04_18_0010.png)

    
20. Now that we have successfully deployed the API , it is time to test the API. Lets make a call to the deployed artifact endpoint. It should throw an error as shown below since the clientkey header is not passed as part of the incoming request as mentioned in step 12

<br>![](/exercises/ex4/images/04_19_0010.png)

21. Add the required header as part of the request.

<br>![](/exercises/ex4/images/04_20_0010.png)

22. Now , we would try to violate the surge protection policy by invoking the same request multiple times and ideally , if we press the send button more than 6 times in span of 10 seconds, the surge protection policy should start blocking the requests.

<br>![](/exercises/ex4/images/04_21_0010.png)






