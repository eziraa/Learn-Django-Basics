## Data Validation

- Django has its data validation
- By default we can not leave ot any space empty even if we made the field nullable in the model designing
- Because we make fields nullable means in the database it cab be null but in the django form we cann't 
- To make fields to be empty we have to add blank =True in the model class

___Example to make promotions and description field to be empty___

```python
class Product(models.Model):
   
    description = models.TextField(null=True, blank=True)
 
    promotions = models.ManyToManyField(
        Promotion, related_name='products', null=True, blank=True)
```

- We can also add data validation on numbers
- Django number validation can not take string or any other than number but it can not validate if we need to exclude -ve numbers

- We can do this by adding validators in the model class 
- Number validator class found in module django.core.validators

___Example___

_Let us ad validation to unit_price and inventory to begin with 1 (not less than 1)_

```python

class Product(models.Model):
   
    # some code goes here
    unit_price = models.DecimalField(
        max_digits=6, decimal_places=2, validators=[MinValueValidator(1)])
    inventory = models.IntegerField(validators=[MinValueValidator(1)])
```

