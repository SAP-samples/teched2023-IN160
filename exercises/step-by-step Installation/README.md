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


1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)

<a href="http://www.youtube.com/watch?feature=player_embedded&v=frIt_8ZsEQQ&t=24s
" target="_blank"><img src="/exercises/ex1/images/01_01_0010.png" 
alt="IMAGE ALT TEXT HERE" width="350" height="280" border="10" /></a>

3.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

