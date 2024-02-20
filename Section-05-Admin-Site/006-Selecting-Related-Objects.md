## Selecting Related Objects

- We can add related objects in the list list_display as follows

```python
@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title', 'unit_price', 'inventory_status', 'collection']
    list_editable = ['unit_price']
    list_per_page = 10
    ordering = ['inventory']
    def inventory_status(self, product):
        if product.inventory < 10:
            return 'Low'
        return 'Ok'
```

- We can also add field name rather than the table name as follows if we want selected field

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title', 'unit_price', 'inventory_status', 'collection__title']
    list_editable = ['unit_price']
    list_per_page = 10
    ordering = ['inventory']
    def inventory_status(self, product):
        if product.inventory < 10:
            return 'Low'
        return 'Ok'
```

- This will select title from the collection class
