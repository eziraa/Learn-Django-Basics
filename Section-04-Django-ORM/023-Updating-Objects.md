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

___Method 2___

- We can fix the above problem by getting object from database rather than creating new one

```python
collection = Collection.objects.get(pk = 1)
collection.featured_product_id = 1
collection.save()
```
- This will fix the above problem

___Method 3___

- We can also update an object by using `update` method

___Example___
```python

collection = Collection.objects.update(featured_product = None)
# This will make all objects featured_product None
# We have to filter we want to update
collection = Collection.objects.filter(pk = 1).update(featured_product = None)
```
