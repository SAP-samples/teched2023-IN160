# Discover, design and run pre-built standard integrations on Edge Integration Cell

Now that you have Activated and deployed an Edge Integration Cell, let's look at how you can Discover, design and run pre-built standard Integrations on Edge Integration Cell. In this exercise you will use a pre-built standard content to connect to S/4 HANA backend system, trigger execution of the content deployed at Edge Integration Cell and perform operations like update of the S/4 data objects.

##  Description

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```



## Description

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
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 4 - Excercise 4 ](../ex4/README.md)

