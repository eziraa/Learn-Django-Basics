## Customizing List Page

- We can customize the admin list page for example by adding new column

___Let use add title and unit_price column to list page of product model___

```python
from .models import Product
from django.contrib import admin

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['titel','unit_price']
```

- If we used decorator as in the above we do not need to register because the decorator already register it

- We can also add list pf editable fields in the above



```python
from .models import Product
from django.contrib import admin

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['titel','unit_price']
    list_editable = ['unit_price']
```

- Then price will be editable in the list page
