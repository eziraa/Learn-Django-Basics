## Executing Raw Executing SQL Query

___Method 1___
- We can run raw SQL queries by using `raw` method the manager of the model


___Example___

```python
queryset = Product.objects.raw('SELECT * FROM store_product')
```
