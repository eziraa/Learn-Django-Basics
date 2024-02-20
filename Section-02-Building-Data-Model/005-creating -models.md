## Creating Models

- Let us create Product class in model module of store app

```python
from django.db import models

# Create your models here.

class Product(models.Model):
    title = models.CharField(max_length = 255)

```
___Explanation___

- First we have to import `models` module from `django.db` module
- Then create a class called `Product` which inherits  `model.Model` model(class)
- Add necessary attributes by specifying their Field type 
- For example as we see in the above the `title`  field has field type of `ChatField`
- There are many field types you can see in django documentation

__Example__
    
    1. CharField
    2. DateField
    3. DatetimeField
    4. BigIntegerField

___Let us update the above Product Model By adding more fields___

```python

from django.db import models

class Product(models.Model):
    title = models.CharField(max_length == 255)
    description = models.TextField()
    price = models.DecimalField(max_digits = 6 , decimal_places = 2)
    inventory = models.IntegerField()
    last_update = models.DateTimeField(auto_now = True)
```

___Let me explain the parameter of the field types___

1. _CharField_
    
    - It has compulsory parameter `max_length` to limit number of characters
2. _DecimalField_
    
    - It has to compulsory parameters `max_digits` and `decimal_places`
        - `max_digits` -> To indicate maximum number of digits in the decimal found 
            
            ___example___
                
                - max_digits = 4 means 345.6 or 52.56 or 2.948
        - `decimal_places` -> to limit decimal places

            ___example___

                - decimal_places = 2 means 234.45 or 34525.57 or 454095.00
3. _DateTimeField_
    - We can set `auto_new` parameter to set its value to the current time and data when it update
    - And we can also set `auto_new_add` parameter to set its value to the current time and data when it is created for first time

___Let us create Customer model___

```python
class Customer(models.Model):
    first_name = models.CharField(max_length=255)
    last_name = models.CharField(max_length=255)
    email = models.EmailField(unique=True)
    phone_number = models.CharField(max_length=255)
    birth_date = models.DateField( null=True)

```

_Let me explain some parameters in the above models_

    - `unique` = `True` the field should be unique no two or more instance of the model to have the field value (means the same email in our current condition)
    - `null` = `True` the field can be null so we can (not providing value to this field)

- When create model in django we don't have to create `id` for our models django add to the model when we create the model
- And it make it primary key 
- But we can also set our primary key manually when we create the model 

___Let us update the Customer model to set the email primary key___

```Python
class Customer(models.Model):
    first_name = models.CharField(max_length =255)
    last_name = models.CharField(max_length = 255)
    email = models.EmailField(unique = True, primary_key = True)
    phone_number = models.CharField(max_length)
    birth_date = models.DateField(null = True)
```
