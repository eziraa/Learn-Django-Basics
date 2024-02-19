## Customizing Forms

- One of best feature of django is giving builin forms to add new objects of models
- As follows 
![Built in Product form](../Images/forms.png)

- We can customize this form by execluding some fields as follows

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    fields = ['title', 'inventory']
```
- This will display only title and inventory fields
![Filtered fields List](../Images/fitlterd.png)

- We can also execlude some fields as follows

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    execludes = ['title', 'inventory']
```
![Execluce Python](../Images/execlude.png)

- We can also make a field readonly

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    readonly_fields = ['title', 'inventory']
```

- Converting dropdown list to autocemplete

- Drop down list of so many objects is bad for optimazation so we should convert it to autp completed

___Example___
- We can convert as drop down list (collection) in product as follows

___Precondition___

    1. str representation of collection class overrided to return its title in Collection class
    2. title attribute should be added to the search field list of CollectionAdmin class
    3. Then add collection to autocomplete_fields list inside ProductAdmin class

- ___Let us do it___

- Overriding str representation method
```python
class Collection(models.Model):
    # other code here
    def __str__(self):
        return self.title
```
- Adding title to search fields

```python
class CollectionAdmin(admin.ModelAdmin):
    # othe code here
    search_fields = ['title']
```

- Then adding colledction to autocomplete_fields list

```python

class ProductAdmin(admin.ModelAdmin):
    autocomplete_fields = ['collection']
```
