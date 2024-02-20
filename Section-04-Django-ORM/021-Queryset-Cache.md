## Query set Cache

- Accessing data from database from disk is expensive
- But accessing data from main memory is faster then the above (also called queryset cache)
- Data stored in queryset cache when is is evaluated
- When queryset evaluated we have see before
    - looping over
    - slicing with step
    - cast to list
    - len
    - repr
    - bool

___Example___
```python

queryset = Product.objects.all() # not evaluated
list(queryset) # evaluated writing to cache
queryset[0] # from catch
```

- Even if caching is nice for optimization code structure is more important

___Let us see below___

```python

queryset = Product.objects.all() # not evaluated
queryset[0] # from disk
list(queryset) # evaluated writing to cache from disk
```
- It hit database two times because even if it evaluated first in indexing but when we cast to list it go to database because all data it require is not in cache