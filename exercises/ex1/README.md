
# Exercise 1 - Access & Explore SAP Integration Suite tenant

In this exercise, you will get access to an SAP Integration Suite tenant, get intorduced to different capabilities and explore navigation across different aspects of SAP Interation Suite tooling.

## Exercise 1.1 Access SAP Integration Suite tenant



1. Click here.
<br>![](/exercises/ex1/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```



## Exercise 1.2 Sub Exercise 1 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.


## Summary

You've now ...

Continue to - [Exercise 2 - Excercise 2 ](../ex2/README.md)
