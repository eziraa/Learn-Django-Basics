## Extending Plugible apps

- Apps in the project have to be self-contained
- Means not to be one depend on other
- For example store app is depend on tag app in the what we have seen before

- To make apps zero-coupling we can use Plugible app
- That means we can create an other app to relate the two model Tag and product

- Let us create new app named `store_custom`

```bash
python manage.py startapp store_custom
```

- The create new `CustomProductAdmin` class which extends `ProductAdmin` class and add the inline class TaggedInline to module `store_custom.admin `

- And the unregister Product model and register CustomProductAdmin

```python
c
class TaggedInline(GenericTabularInline):
    autocomplete_fields = ['tag']
    model = TaggedItem


class CustomProductAdmin(ProductAdmin):
    inlines = [TaggedInline]


admin.site.unregister(Product)
admin.site.register(Product, CustomProductAdmin)

```