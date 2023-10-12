# Step-by-step installation of Edge Integration Cell

In this exercise, we will follow along with a recorded step-by-step video that takes us through the Edge Integration Cell installation. 

## System pre-requisites

The installation assumes that the following pre-requisites have been met:
1.  First and foremost, we will need privileges to create Kubernetes Service in either EKS, AKS, or SuSE Rancher / RKE2. Please work with your internal IT teams to get hold of these.
2.  Optional - Kubernetes command line tool : kubectl, to dig into some of the internals. 
3.  A technical user (P-User) already exists. The setup process performs an implicit Cloud Connector installation during the Kubernetes bootstrapping process. Pls note that Cloud Connector comes in only for the management plane flows (and not during the actual API / IFlow execution)
4.  An S-user already exists. Using this S-User, a technical user in SAP Repositories Management  https://ui.repositories.cloud.sap/ will be created. This process is needed during the transfer of the code binaries from SAP's central repository to the customer's designated Container Registries.
5.  Optional - To enable central system monitoring, an Identity Authentication Service (IAS) tenant exists.
6.  A private key and a CA-signed certificate that we will use to establish HTTPS on the Istio Ingress Gateway
7.  Control of DNS registry in order to perform an A-record mapping of the Load Balancer IP with the virtual host alias that is established in the step above.

These are only few highlights and by no means an exhaustive list of system prerequisites needed to perform an end-to-end installation. Our help documentation : https://help.sap.com/docs/integration-suite/beta-edge-integration-cell/before-you-start?version=CLOUD  will cover the system prerequisites, supported software versions, network dependencies etc. Please keep an eye on that space 




## Installation Video

Here is the link to the video : <br> <br>
<a href="http://www.youtube.com/watch?feature=player_embedded&v=frIt_8ZsEQQ" target="_blank"><img src="http://img.youtube.com/vi/frIt_8ZsEQQ/0.jpg" alt="IMAGE ALT TEXT HERE" width="700" height="560" border="10" /></a>

## Setup steps

Colons can be used to align columns.

| Step No        | Detail           | Timestamp  |  Video link <img width=1400/>|
| -------------- |:----------------| ----------| :------------------------------|
| 1     | <ins>Activate Edge Integration Cell feature </ins> <br><br> In the Integration Suite landing page, you will see there is a new 'Runtime' section within 'Settings'. This section holds the step to activate the 'Edge Integration Cell' feature. Under the hood, it creates a subscription to a capability called 'Edge Lifecycle Management' (ELM), the management or the control plane that controls the lifecycle of the Edge runtime nodes | 0:0 - 0:24 sec | <a href="http://www.youtube.com/watch?feature=player_embedded&v=frIt_8ZsEQQ" target="_blank"><img src="http://img.youtube.com/vi/frIt_8ZsEQQ/0.jpg" alt="IMAGE ALT TEXT HERE" width="350" height="280" border="10" /></a> |
| 2      | <ins>Setup the Role Collection needed to access the ELM.</ins> <br><br> First, we create a role collection, say 'EdgeLMAccess', and assign the newly available role named 'EdgeLMAccess'. After this, we assign the email address of the technical P-User mentioned in step 3 of the pre-requisites section to this Role Collection. Next, head over to the Cloud Connector Administrator Role Collection and make sure the same user has this assignment as well. These are two mandatory steps. |   1:39 | <a href="http://www.youtube.com/watch?feature=player_embedded&v=frIt_8ZsEQQ&t=24s" target="_blank"><img src="http://img.youtube.com/vi/frIt_8ZsEQQ/0.jpg" alt="IMAGE ALT TEXT HERE" width="350" height="280" border="10" /></a> |
| zebra stripes | are neat      |    $1 | <a href="http://www.youtube.com/watch?feature=player_embedded&v=frIt_8ZsEQQ&t=24s" target="_blank"><img src="http://img.youtube.com/vi/frIt_8ZsEQQ/0.jpg" alt="IMAGE ALT TEXT HERE" width="350" height="280" border="10" /></a> |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

