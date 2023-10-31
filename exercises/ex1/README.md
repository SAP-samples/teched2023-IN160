
# Exercise 1 - Access and explore SAP Integration Suite

In this exercise, you will 
- get access to an SAP Integration Suite tenant,
- get introduced to different capabilities and explore navigation across different aspects of SAP Interation Suite tooling.

## Access SAP Integration Suite tenant

For running through the exercise steps, you will need access to SAP Integration Suite tenants. Please pick one of these SAP Integration Suite tenant as per the assignment . You will also get the credentials to log in to these tenants from the instructors.

1. Please use this **SAP Integration Suite tenant** for your exercises
      - https://iat-prism-std.integrationsuite-it-ziat003.cfapps.eu21.hana.ondemand.com/shell/home

2. Use the **username** and **password** shared by the instructors to login to the tenant assigned to you

3. For Exercise 3 and Exercise 4, please use these Service Instance credentials

   
## Explore SAP Integration Suite tooling

Log in to SAP Integration Suite tenant using the credentials provided to you by the instructors. Now let´s explore the different capabilties and navigations of SAP Integration Suite tooling

**Home** is the first screen that you will land upon logging in to SAP Integration Suite. Click on the three lines icon on the top left corner to expland the navigation menu items.

<br>![](/exercises/ex1/images/Home.jpg)<br><br><br>


First section is the **Recent Activities & Monitoring**, which gives you a snapshot of what´s going on with the SAP Integration Suite tenant. It lists the artifacts that were worked upon and also the monitoring status of the deployed artifacts. You can navigate to them directly from here.

<br>![](/exercises/ex1/images/Home-Recent.jpg)<br><br><br>


Then you will see the list of **Capabilities** that are activated in this tenant. SAP Integration Suite provides many different capabilities like Cloud Integration, API Management, Integration Advisor, Trading Partner Management, Open Connectors, Integration Assessment and Migration Assessment, to address all your integration requirements.

<br>![](/exercises/ex1/images/Home-Capabilities.jpg)<br><br><br>


Last section of the Home page is the **Learning & Feedback**, where links to documentation, tutorials, and also an option to request for addititional features.

<br>![](/exercises/ex1/images/Home-Resources.jpg)<br><br><br>


Now if you look at the different navigation sections on the left, after **Home**, you will see **Discover**, which is a repository of all standard pre-built content (integrations, APIs and type systems) shipped by SAP. Based on your specific integration need, you can explore, search and copy them to your **Design** workspace to kick-start your integration development.

<br>![](/exercises/ex1/images/Discover.jpg)<br><br><br>


**Design** is your local workspace where you can design and configure integrations, APIs, message implementation guidelines, mapping guidelines, scripts and other integration artifacts.

<br>![](/exercises/ex1/images/Design.jpg)<br><br><br>


**Test** your APIs and analyse the response you get from them

<br>![](/exercises/ex1/images/Test-APIs.jpg)<br><br><br>


Use this section to **Configure** API Providers, Certificates and Key Value Mappings for your APIs

<br>![](/exercises/ex1/images/Configure-APIs.jpg)<br><br><br>


In the **Monitor** section, you can check the deployment status, look at message processing logs, manage security materials, data stores, message queues and all that you need to monitor and operate your integrations.

<br>![](/exercises/ex1/images/Monitor-Integration.jpg)<br><br><br>


**Inspect** enables you to assess the overall resource situation of the tenant, like identifying hotspots, breakdown of resource consumed by each integration flow, resource usage trends.

<br>![](/exercises/ex1/images/Inspect.jpg)<br><br><br>


You can use **Monetize** to define rate plans for the API Products that you build and check the API usage pattern. The in-built billing engine also generates the bills for you, which can be accessed across multiple channels.

<br>![](/exercises/ex1/images/Monetize.jpg)<br><br><br>


If you have Tenant Admin role assigned, you will be able to access **Settings**. Here you can configure settings which are applicable for the entire tenant like managing runtime profiles, configuring transport management, setting up API Management, customization of MIGs & MAGs, etc.

<br>![](/exercises/ex1/images/Settings-Integrations.jpg)<br><br><br>


Under **Settings - Runtime**, you will be able to activate or deactivate "Edge Integration Cell" and for this you need to have "Integration_Provisioner" role assigned to your user. Once "Edge Integration Cell" is activated, you will get a URL to navigate to "Edge Lifecycle Management", which is required to setup and deploy Edge Integration Cell to your kubernetes cluster. To access "Edge Lifecycle Management", you will need "EdgeLMAccess" role.

<br>![](/exercises/ex1/images/Settings-Runtime.jpg)<br><br><br>


## Summary

You now have access to an SAP Integration Suite tenant and have explored the tooling and different navigation aspects.

Continue to - [Exercise 2 - Activate and deploy Edge Integration Cell](../ex2/README.md)
