## Referencing Fields Using F Objects

- How to reference fields in filter method for example if we want to get products whose unit price is equal to inventory
- Can use as this ?
```python
products = Product.objects.filter(unit_price = inventory)
```
- Answer: No 
- Because if we use as this we encounter an error inventory does not defined before
- So to reference other field we have to use F class object
- F refers to Field

```python
from django.db.models import F

products = Product.objects.filter(unit_price = F('inventory'))
```