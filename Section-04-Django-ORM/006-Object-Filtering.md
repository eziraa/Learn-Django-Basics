## Object Filtering

- We can filter objects when we retriving objects 
- By using filter method we can filter
- filter method takes keyword args to work correctly

___Exmaple___

1. find an object which has unit price 20 

    - We can get those objects as follows

    ```python 
    products = Product.objects.filter(unit_price = 20)
    ```

    
