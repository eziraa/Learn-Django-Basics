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

___Let us modify the Address model to add the relation ship___

```python
class Address(models.Model):
    street = models.CharField(max_length = 255)
    city = models.CharField(max_length = 255)
    customer = models.OneToOneField(Customer, on_delete = models.CASCADE, primary_key =True)
```

- When we create the relationship  we pass to argument
    - 1st argument is to indicate the paretn class
    - 2nd argument is `on_delete` specify what should going on the child model when the parent model deleted
        - `on_delete` has the following value

            - `models.CASCADE `-> delete it
            - `models.SET_NULL` -> set null 
            - `models.SET_DEFAULT `-> set its default value
            - `models.PROTECT` -> raise Exception to do not delete the parent first delete the child
    - 3rd argument is primary_key
        - If we do not set this value django create id for the model and use that id for primary key and the table can store an address for different customer 
        - And this make many-to-many relationship not one-to-one relationship 
        - Finally we have to set the customer as primary_key to resolve duplicate

___After we set  one side relationship then django create the reverse relationship___