## Complex Query Filtering with Q objects

- We can chain filters on queryset and pass many lookup argument and do complex query 

___Example___

```python
q1 = Product.objects.filter(unit_price__gt = 10, unit_price__lt = 20)

q2 = Product.objects.filter(unit_price__gt = 10).filter(unit_price__lt = 20)

```
- Then above code is replacement of 'AND' like (products whose unit_price is greate than 10 and less than 20)

- But how to use `OR` like (products whose unit_price is greate than 30 and less than 20)
- To get objects combined by  `OR` we can use `Q` class objects and bitwise operator `|`
- For `AND` use `&`
- Q means query whose result is value

___Example___

```python
from django.db.models import Q
q = products.objects.filter(Q(unit_price__gt = 10) & Q(unit_price__lt = 20))

# This is equivalent to the above chaing filters
# It will return products whose unit_price is greate than 10 and less than 20

q = products.objects.filter(Q(unit_price__gt = 30) | Q(unit_price__lt = 10))

# This return products whose unit_price is greate than 30 and less than 20
```