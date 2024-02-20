## Sorting

- We can sort our queryset by using order_by method as follows 
- It can sort ascending by default

```python
ordered_products = Product.objects.order_by('title')
```

- And we can sort in descending order by add - sign before the filed name

```python
ordered_products = Product.objects.order_by('-title')
```

___Sorting in multiple fields___

- We can sort queryset by giving multiple field

_Example_

```python
products = Product.objects.order_by('unit_price', '-inventory')

# It sort the query set by their unit price then by inventory
```

- We can also call method called `reverse`  on ordering then it will reverse the ordering

```python 
reversed_products = Product.objects.order_by('title').reverse()

# it will return reversed order of products
```
- Order by method return a query set so  we can chain  others method on it
- for example how to get the first product after ordered by their title

```python
product = Product.objects.order_by('title')[0]

# we get single object because we used slicing 

```

- And we can also use `earliest` method instead of slicing and order by

```python
product = Product.objects.earliest('title')

# This also return a single object
```
- We can also use latest method to return the last object

```python
product = Product.objects.latest('title')
# This also return a single object
```


