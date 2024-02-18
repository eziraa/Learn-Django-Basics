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


