## Adding Custom Action

- By defaut the admin site has delete action but we can add other action
- Let us add an action which clear inventory
- To add first add custom action method to clear inventory in the ProductAdmin class
Than add this method in the list of action in ProductAdmin class

```python

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    actions = ['clear_inventory']
    list_display = ['title', 'unit_price', 'inventory_status', 'collection']
    list_editable = ['unit_price']
    list_per_page = 10

    list_filter = ['collection', 'last_update', InventoryFilter]
    ordering = ['inventory']

    def inventory_status(self, product: Product):
        if product.inventory < 10:
            return 'Low'
        return 'Ok'

    @admin.action(description='Clear Inventory')
    def clear_inventory(self, request, queryset: QuerySet):
        updated_count = queryset.update(inventory=0)
        self.message_user(
            request,
            f'{updated_count} products were updated successfully'
        )
```

- We can also specify message type as third parameter of the custom action mesthod by importing `messages` module from django.contrib module

```python

 @admin.action(description='Clear Inventory')
    def clear_inventory(self, request, queryset: QuerySet):
        updated_count = queryset.update(inventory=0)
        self.message_user(
            request,
            f'{updated_count} products were updated successfully',
            messages.SUCCESS
        )
```