## Grouping Data

- We can group data based on the their relationship to other table
- For example We can find number of orders ordered by one customer to find those we can use grouping
- To gouping we use Count `class`

```python
from django.db.models.functions import Count
customers = Customer.objects.annotate(Number_Of_Orders = Count('order') )

# use `order` instead of order_set to indicate order
```

- This will additional field called `Number_Of_Orders` with a value number of orders ordered by a Customer