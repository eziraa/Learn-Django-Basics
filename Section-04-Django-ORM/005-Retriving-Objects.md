## Retriving Objects

- To retrive objects from database we can use the following methods

___Example___
- To retrive all objects of the model use `all` method


```python
productQuerySet = Product.objects.all()
```
- To retrive an object you can use `get`method

```python
productQuerySet = Product.objects.get(id = 1)
```
- You can also use `pk` instead of `id` to indicate primary key of the table
- When we use pk in django transform pk to the name of the primary key

```python
productQuerySet = Product.objects.get(pk = 1)
```