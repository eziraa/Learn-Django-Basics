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