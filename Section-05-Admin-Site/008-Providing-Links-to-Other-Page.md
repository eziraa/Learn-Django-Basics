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
    
    # This method is inherited from ModelAdmin class 
    def get_queryset(self, request):
        return super().get_queryset(request).annotate(products_count=Count('product'))
```

- Let us modify the above method to return the correct link to navigate to product changelist

- By importing `reverse` method from `django.urls` module

- When we call reverse method the format is as follows

- admin:<app_name>_<model_name>_<page_name>

    - _app_name_ -> store
    - _model_name_ -> product
    - _page_name_ -> changelist



```python
from django.utils.html import format_html
from django.db.models.aggregates import Count
from django.urls import reverse
@admin.register(Collection)
class CollectionAdmin(admin.ModelAdmin):
    list_display = ['title', 'products_count']

    def products_count(self, collection):
        url = reverse('admin:store_product_changelist')
        return format_html('<a href = "{}">{}</a>',url, collection.products_count)
    
    # This mathod is inheited from ModelAdmin class 
    def get_queryset(self, request):
        return super().get_queryset(request).annotate(products_count=Count('product'))
```

- Let us make the above code to return the list of products which found in that collection only by filtering in collection id

```python
from django.utils.html import format_html
from django.db.models.aggregates import Count
from django.urls import reverse
@admin.register(Collection)
class CollectionAdmin(admin.ModelAdmin):
    list_display = ['title', 'products_count']

    def products_count(self, collection):
        url = reverse('admin:store_product_changelist'
        + '?'
        + 'collection_id={}'.format(collection.id))
        return format_html('<a href = "{}">{}</a>',url, collection.products_count)
    
    # This mathod is inheited from ModelAdmin class 
    def get_queryset(self, request):
        return super().get_queryset(request).annotate(products_count=Count('product'))
```

- This will navigate us to the list of collection products only 