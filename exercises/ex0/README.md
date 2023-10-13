# Getting Started

In this exercise, you will learn and get an overview of SAP Integration Suite and Edge Integration Cell. This will set the context and help you execute the rest of the exercises.

## What is SAP Integration Suite?

After completing these steps you will have....

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
