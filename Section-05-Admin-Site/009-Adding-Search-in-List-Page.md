## Adding Search in List Page

- we can add search fields in lits page
- Let us add search fields like first_name and last_name to search_fields attribute of the CustomerAdmin Class

```python
@admin.register(Customer)
class CustomerAdmin(admin.ModelAdmin):
    list_display = ['first_name', 'last_name', 'membership' ]
    list_editable = ['membership']
    search_fields = ['first_name', 'last_name']
```
- This will add search field on the top of the list page 
- But if we want to search and enter some text then it will check weather the first_name or last_name contain that text of it contain it will display the customer

- We can add lookup on the field name to make our search meaningfull 

___Let us add lookup on the fields___

```python
@admin.register(Customer)
class CustomerAdmin(admin.ModelAdmin):
    list_display = ['first_name__startswith', 'last_name__startswith', 'membership' ]
    list_editable = ['membership']
    search_fields = ['first_name', 'last_name']
```

- But the above lookups are case sensetive if we want to make case insensetive we can append `i` before the lookups

___Let use modify it___

```python
@admin.register(Customer)
class CustomerAdmin(admin.ModelAdmin):
    list_display = ['first_name__istartswith', 'last_name__istartswith', 'membership' ]
    list_editable = ['membership']
    search_fields = ['first_name', 'last_name']
```
