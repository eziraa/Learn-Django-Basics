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

