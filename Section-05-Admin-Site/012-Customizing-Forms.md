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