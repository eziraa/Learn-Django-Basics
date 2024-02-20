## Circular Relationship

- Circular Relationship mean when two models depend on each other

___Example___

- If we add a field called featured product to collection class
```python
class Collection(models.Model):
    title = models.CharField(max_length=255)
    featured_product = models.ForeignKey(Product,on_delete = models.SET_NULL. null = True)
```

- This code raise an error because two models are depend one each other during making reverse relationship

- We can solve this as follows by make the related_name their character and the related model name normal string

```python
class Collection(models.Model):
    title = models.CharField(max_length=255)
    featured_product = models.ForeignKey('Product',on_delete = models.SET_NULL. null = True, related_name = '+')
```
