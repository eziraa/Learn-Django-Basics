## Deleting Objects

- We can delete one object or multiple object

___Deleting one object by creating object___

```python

collection = Collection(pk = 1)
collection.delete()
```
___Deleting one or more object by using `filter` method

- We can delete multiple objects by using `filter`  and `delete` method

```python
Collection.objects.filter(id__lt = 5).delete()

```
- This will delete all collection objects whose id is less than 5

