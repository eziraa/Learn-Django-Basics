## Creating Models

- Let us create Product class in model module of store app

```python
from django.db import models

# Create your models here.

class Product(models.Model):
    title = models.CharField(max_length)
```
___Explanation___

- First we have to import `models` module from `django.db` module
- Then create a class called `Product` which inherits  `model.Model` model(class)
- Add neccessary attributes by specifing their Field type 
- For example as we see in the above the `title`  field has field type of `ChatField`
- There are many field types you can see in django decumentation

__Example__
    
    1. CharField
    2. DateField
    3. DatetimeField
    4. BigIntegerField