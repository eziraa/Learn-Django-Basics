## Providing links to other Page

- We can provide links to other page when we click some value from the list page

- Let us change the method `products_count` to return link instead of value by importing format_html from html module

```python
from django.utils.html import format_html
from django.db.models.aggregates import Count

@admin.register(Collection)
class CollectionAdmin(admin.ModelAdmin):
    list_display = ['title', 'products_count']

    def products_count(self, collection):
        return format_html('<a>{}</a>', collection.products_count)
    
    # This mathod is inheited from ModelAdmin class 
    def get_queryset(self, request):
        return super().get_queryset(request).annotate(products_count=Count('product'))
```
