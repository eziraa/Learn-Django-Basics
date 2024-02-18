## Complex Query Filtering with Q objects

- We can chain filters on queryset and pass many lookup argument and do complex query 

___Example___

```python
q1 = Product.objects.filter(unit_price__gt = 10, unit_price__lt = 20)

q2 = Product.objects.filter(unit_price__gt = 10).filter(unit_price__lt = 20)

```
- Then above code is replacement of 'AND' like (products whose unit_price is greate than 10 and less than 20)
