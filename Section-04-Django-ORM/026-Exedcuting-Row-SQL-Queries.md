## Executing Raw Executing SQL Query

___Method 1___
- We can run raw SQL queries by using `raw` method the manager of the model


___Example___

```python
queryset = Product.objects.raw('SELECT * FROM store_product')
```

___Method 2___

- We can execute any type of SQL Query by creating cursor object as follows

```python

from django.db import connection
cursor = connection.cursor()
cursor.execute('SELECT * FROM store_product')
queryset = cursor.fetchall()
cursor.close()

```
