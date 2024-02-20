## Customizing ModelAdmin Queryset

- There is a queryset returned by `get_queryset` method of `ModelAdmin`
- And we can customize this queryset as we want 
    - ___Filter___
    - ___Group___
    - ___Sort___

___Let us add products_count column on collection list page___

```python

@admin.register(Collection)
class CollectionAdmin(admin.ModelAdmin):
    list_display = ['title', 'products_count']

    def products_count(self, collection):
        return collection.products_count
```

- We can add computed column called `products_count` by defining  function by the name of computed column

- But there is a problem there is no `products_count` field in collection model so we have to annotate this column name by customizing the queryset

- _Let us customize `get_queryset` method_

```python

from django.db.models.aggregates import Count

@admin.register(Collection)
class CollectionAdmin(admin.ModelAdmin):
    list_display = ['title', 'products_count']

    def products_count(self, collection):
        return collection.products_count
    
    # This mathod is inherited from ModelAdmin class 
    def get_queryset(self, request):
        return super().get_queryset(request).annotate(products_count=Count('product'))
```

- This will add new computed column called `products_count`
