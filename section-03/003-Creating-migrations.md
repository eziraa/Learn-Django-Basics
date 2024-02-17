## Creating migrations 

- First what is migration?
- Migration is a file that create or update or database table based on our current model
- To create migration there must model or change on model because the mogration is used to reflect change on model to out database tables
- Models we created before are not stored to the database to store those model or simply to create table that represent our model we havr to create migration
- To create migration we use the following command

```bash
 python manage.py makemigrations
```
 ___Remember___
 
 - This command ceate migration only for apps that are found in `INSTALLE_APPS` list so ___do not forget to add your apps to this list___

___Command Trick___
    
    To find come symbol like(Product, Customer, Order ...) you can use `CTRL + T` and type your symbol

- You can modify some model and make new migration 
- Let us rename `price` to `unit_price` in `Product` model

```python
    price = models.DecimalField(max_digits=6, decimal_places=2)
```
- Then rerun the above command

```bash
 python manage.py makemigrations
```

- You will get new migration file in store app inside migrations folder
- And if you want to rename the migration file name fell free you can but if you modify the content of the migration file it will have effect on the database so be sure to modify correctly its content




