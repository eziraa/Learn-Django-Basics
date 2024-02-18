## Sorting

- We can sort our queryset by unsing order_by methd as follows 
- It can sort ascendingly by default

```python
ordered_products = Product.objects.order_by('title')
```

- And we can sort in descending order by add - sign before the filed name

```python
ordered_products = Product.objects.order_by('-title')
```
