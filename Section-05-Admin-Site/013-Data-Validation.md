## Data Validation

- Django has its data validation
- By default we can not leave ot any space empty even if we made the field nullable in the model designing
- Because we make fields nullable means in the database it cab be null but inthe django form we cann't 
- To make fields to be empty we have to add blank =True in the model class

___Example to make poromotios and description field to be empty___

```python
class Product(models.Model):
   
    description = models.TextField(null=True, blank=True)
 
    promotions = models.ManyToManyField(
        Promotion, related_name='products', null=True, blank=True)
```
