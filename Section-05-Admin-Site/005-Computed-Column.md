## Computed Column

- We can add computed column by creating new method that compute some result 

___Example__

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title', 'unit_price', 'inventory_status']
    list_editable = ['unit_price']
    list_per_page = 10
    ordering = ['inventory']
    def inventory_status(self, product):
        if product.inventory < 10:
            return 'Low'
        return 'Ok'
```

