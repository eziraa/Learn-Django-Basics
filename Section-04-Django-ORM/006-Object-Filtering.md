## Object Filtering

- We can filter objects when we retrieving objects 
- By using filter method we can filter
- filter method takes keyword args to work correctly

___Example___

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

    - a keyword argument unit_price__gt means unit_price > 20

___Key word argument trick for number related___

- _Let the field name is unit_price then_
    1. _Concatenate `__gt` for greater than_
    2. _Concatenate `__lt` for less than_
    3. _Concatenate `__gte` for greater than or equal to_
    4. _Concatenate `__lte` for less than or equal to_

___Key word argument trick for all field type___

- Filter method takes arbitrary number of keyword args
- The format of those  keyword args is as follows

    - field name__lookuptypes = value

_Example_
- field name = title
- look up type = startswith

then arg is `title__startswith = 'e'`

- But there is an exception for the above format for foreign key id use one underscore as follows

```python

order = Order.objects.filter(customer_id = 2)

```

___More look ups___

- _exact_ -> to return the something exact equal to its value

    _Example_

    ```python
     order = Order.objects.filter(title__exact = 'order1')
     ```
- _iexact_ -> it is the same to the above lookup but it is case insensitive

- _contains_ -> to check the value contains some value

    _Example_

    
    ```python
     order = Order.objects.filter(title__contains = 'order')
     ```

- _icontains_ -> this is the same as `contains` method but this is case insensitive

- _startswith_ -> to check the object field contains the value
- _istartswith_ -> The same to above but it is case insensitive

- _endswith_ -> to check wether the field of the object end with the value_

- _iendswith_ -> This is the same to endswith lookup but it is case insensitive
- _year_ -> To return objects of the year
- _date_ -> To return objects of the day
- _range_ -> To return objects between range(especially for number related)

___Remember___

- When we filter, execute, sort, group query set is not evaluated simply i constructs an other query 

_Example_

```python 
q1 = Products.objects.all()
q2 = q1.filter(unit_price__gte = 20)
q3 = q2.filter(unit_price__gte = 30)
print(q3)
```

- As we see in the above we will think the queryset hit the database three times.
- But we are wrong because a queryset hit the database when it is evaluated
- So it hit the database when it reaches to print method


- Querysets are lazy why?
- There lazy means they don't hit the database until evaluated which means if our action have so many filter then it can not br evaluated before filter finish
- It waits until the filtration finished

___Let us see when query evaluated___

1. _Iteration_
    - When we iterate over queryset then the queryset evaluated
2. _Slicing_
    - Slicing unevaluated queryset return unevaluated Queryset
    - But when we slice queryset if we add `step` parameter it return evaluated list of queryset
    - Slicing evaluated queryset also return list

    _Remember_
    - Even if Slicing unevaluated queryset return unevaluated Queryset filtering further is not allowed 

3. Pickling/Caching.
    - if we pickle a queryset then all results to be evaluated and loaded to memory before pickling
4. repr()
    - If we call `repr` function on it the queryset evaluated

5. len()
    - If we want to know length of the queryset and we call len() method then the queryset evaluated
6. bool()
    - Testing a QuerySet in a boolean context, such as using bool(), or, and or an if statement, will cause the query to be executed.
7. list
    if we cast queryset to list then the query set evaluated


