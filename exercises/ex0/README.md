# Getting Started

Let´s start with an overview of SAP Integration Suite and Edge Integration Cell. This will set the context and help you execute the rest of the exercises.

## What is SAP Integration Suite?

SAP Integration Suite is an Enterprise integration platform-as-a-service (EiPaaS) that helps to quickly integrate on-premise and cloud-based processes, services, applications, events, and data. 

Key highlights:
- Prebuilt integrations managed and updated by SAP
- Harmonized access to popular third-party cloud applications
- Tools for designing, publishing, and managing APIs
- AI-assisted development and integration optimization
- Tools-based, guided approach to define, document, and govern your integration strategy

<br>![](/exercises/ex0/images/IS.jpg)

## What is Edge Integration Cell and how it enables Hybrid Integrations?

1.	Click here.
<br>![](/exercises/ex0/images/00_00_0010.png)

2.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
