## Updating objects

- We can update objects ad follows by uisng its pk

___Method 1___

```python

collection = Collection(pk = 1)
collection.title = 'Video games'
fetured_product_id = 1
collection.save()

```
- The above code update a collection object if t found by testing id attribute

- The above code will create a problem when we update some field of the object
- Then django will update what we updated and set empty for the other fields 
- Because in the above code it is simply creating collection object and when we save djnago see weather the object id exist in the database or not 
- Then if exist it replaced the object by this object 
- So if we miss some field unupdated we lost data

__Let us example__

```python

collection = Collection(id = 1)
collection_product_id = 2
collection.save()
```
- We will lost `title` for the above object