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
- For any operation the cursor needs to be closed to release its resources

- If there is an exception during execution of the query thr cursor can not be closed

- So to close foy any putput we should use try, finally block

```python

from django.db import connection
try:
    cursor = connection.cursor()
    cursor.execute('SELECT * FROM store_product')
    queryset = cursor.fetchall()
except Exception:
    pass
finally:
    cursor.close()

```

 - Rather than closing the cursor object manually the efficient way is to use is with `with` block 

```python


from django.db import connection
with connection.cursor() as cursor:
    cursor.execute('SELECT * FROM store_product')
    queryset = cursor.fetchall()
```