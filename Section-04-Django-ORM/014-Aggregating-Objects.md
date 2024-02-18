## Aggregating Objects

- Aggregating means do some action on to all instance of table and return single result

_Exmaple_

1. _count_
2. _min_
3. _max_
4. _average_
5. _sum_

- To  aggregating objects we use method called `aggregate`
- By Importing the aggregatin class like `Count`, `Max`, `Min`, `Avg`, and `Sum` from `django.db.models.aggregates`


___Example___

```python

number_of_products = Product.objects.aggregate(Count('id'))

avg_unit_price = Product.objects.aggregate(Avg('unit_price'))
```
