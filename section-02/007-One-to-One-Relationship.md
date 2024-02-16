## One to One realtionship 
- Create Address model  in the model module of store app

```Python
class Order(models.Model):
    street = models.CharField(max_length = 255)
    city = models.CharField(max_length = 255)
```

- This is noraml model

- How to implement one to one relationship between the address model to Customer model
- In this relation ship there are to things `parent`
and `child` 
- `Parent` should be difined before `child`
- In this relation the parent is `Customer` model
and child is `Address` model

___Remember___
    
    don't be confused with `class` and `model`
    because both are almost the same