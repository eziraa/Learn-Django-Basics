## Creating Objects

- We create and save objects in ORM instead `INSERT INTO ` statement of SQL

- We create as follows

___Method 1___

```python
collection = Collection(title = 'Video Games', featured_product = Product(pk =1))

# OR use id instead of pk
collection = Collection(title = 'Video Games', featured_product = Product(id =1))

# OR use featured_product_id instead of featured_product

collection = Collection(title = 'Video Games', featured_product_id = 1)

# Then save
collection.save() # this is equivalent to INSERT INTO
```
