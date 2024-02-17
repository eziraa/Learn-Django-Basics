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

___Key word argumnet trick for all field type___

- Filter method takes arbitrary number of keyword args
- The format of those  keyword args is as folloes

    - field name__lookuptypes = value

_Example_
- field name = title
- look up type = startswith

then arg is `title__startswith = 'e'`

- But there is an exception for the above format for foreignkey id use one underscore as folows

```python

order = Order.objects.filte(customer_id = 2)

```

___More look ups___

- _exact_ -> to retrun the somethind exact equal to its value

    _Example_

    ```python
     order = Order.objects.filter(title__exact = 'order1')
     ```
- _iexact_ -> it is the same to the above lookup but it is case insensetive

- _contains_ -> to check the value containe some value

    _Example_

    
    ```python
     order = Order.objects.filter(title__contains = 'order')
     ```

- _icontains_ -> this is the same as `contains` method but this is case insensetive

