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

 7. Click on Edit and navigate to the policy tab and this is how the starter content should look like. As you can see the Authentication policy appears by default. Double click on the authentication policy and navigate to the property sheet at the bottom. By default Basic is not enabled and as an exercise, you should enable the Basic checkbox from the multi-select drop-down

 <br>![](/exercises/ex4/images/04_07_0010.png) 

 8. Click on the Authentication policy and you should see a pop-up with a set of actions. Click on the "+" icon

 <br>![](/exercises/ex4/images/04_08_0010.png) 

 9. Select the surge protection policy from the drop-down and add the Surge protection policy. The policy protects the target endpoint from a sudden spike in incoming requests

<br>![](/exercises/ex4/images/04_09_0010.png) 

10. Navigate the surge protection policy and add the required details. The current configuration allows 6 calls over a span of 10 seconds
    
<br>![](/exercises/ex4/images/04_10_0010.png) 

11. Click on the Surge Protection policy and you should see a pop-up with a set of actions. Click on the "+" icon and select Quota

<br>![](/exercises/ex4/images/04_11_0010.png)  
    
