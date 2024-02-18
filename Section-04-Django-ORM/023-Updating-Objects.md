## Updating objects

- We can update objects ad follows by uisng its pk

___Method 1___

```python

collection = Collection(pk = 1)
collection.title = 'Video games'
fetured_product_id = 1
collection.save()

```
