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

___Let us update the above Product Model By adding more fields___

```python

from django.db import models

class Product(models.Model):
    title = models.CharField(max_length)
    description = models.TextField()
    price = models.DecimalField(max_digits = 6 , decimal_places = 2)
    inventory = models.IntegerField()
    last_update = models.DateTimeField(auto_now = True)
```

___Let me explain the parameter of the field types

1. _CharField_
    
    - It has complusory parameter `max_length` to limit nomber of charchters
2. _DecimalField_
    
    - It has to complusory parameters `max_digits` and `decimal_places`
        - `max_digits` -> To indicate maximum number of digits in the decimal found 
            
            ___example___
                
                - max_digits = 4 means 345.6 or 52.56 or 2.948
        - `deciaml_places` -> to limit deciaml places

            ___exampl___

                - decimal_places = 2 means 234.45 or 34525.57 or 454095.00


