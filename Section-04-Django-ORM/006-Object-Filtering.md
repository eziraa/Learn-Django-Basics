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
2. What if we need objects which has objects unit_price greater than 20
    - We can get those objects as follows

    ```python 
    products = Product.objects.filter(unit_price__gt = 20)
    ```

    - a keyword argument unit_pricee__gt means unit_price > 20

___Key word argumnet trick for number related___

- _Let the field name is unit_price then_
    1. _Concatinate `__gt` for greater than_
    2. _Concatinate `__lt` for less than_
    3. _Concatinate `__gte` for greater than or equal to_
    4. _Concatinate `__lte` for less than or equal to_

    
