## Selecting Feilds

- We can select some fields only when we extract data from database by specifing the fields in value `mathod`

___Example___

```python
products = Product.objects.value('id', 'description')

# This will return only the id and description of the products
```
___Remember___

-This will return a banch of dictionary objects rather than banch of queryset instances

- And even if it returns a banch of dictionary object we can chaing other methods

- To return a banch of tuple instead of dictionary  we can use method `value_list` instead of `values`

___Example___

```python
products = Product.objects.value_list('id', 'description')

# It will return a banch of tuple that represent product instance
```

___Question___
- Select all producst that have been ordered and sort the by title

___Solution___

```python
ordered_products_id = OrderItem.objects.values_list('product_id').distinct()
ordered_products = Product.objects.filter(
        id__in=ordered_products_id).order_by('title')

```

___Explanation__
- id__in -> means id found in the tuple of the order_products_id ( look for SQL codde `something IN some range()` )
- distinct -> to return not repeated result

