## Adding Filtering

- We can add fields wich we want to filter our list 

- Let us add filtering by collection and last_update on product list page

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title', 'unit_price', 'inventory_status', 'collection']
    list_editable = ['unit_price']
    list_per_page = 10
    list_filter = ['collection', 'last_update']
    ordering = ['inventory']
    def inventory_status(self, product):
        if product.inventory < 10:
            return 'Low'
        return 'Ok'
```
- This will make builin filtering lists tob displayed on the right side as follows

![Filtering Page](../Images/filter.png)
