## Customizing List Page

- We can customize the admin list page for example by adding new column

___Let use add title and unit_price column to list page of product model___

```python
from .models import Product
from django.contrib import admin

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title','unit_price']
```

- If we used decorator as in the above we do not need to register because the decorator already register it

- We can also add list pf editable fields in the above



```python
from .models import Product
from django.contrib import admin

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title','unit_price']
    list_editable = ['unit_price']
```

- Then price will be editable in the list page


- We can also change list per page to be displayed ad follows

```python
from .models import Product
from django.contrib import admin

@admin.register(Product)
class ProductAdmin(admin.ModelAdmin):
    list_display = ['title','unit_price']
    list_editable = ['unit_price']
    list_per_page = 10
```

___Exercise on Customer model___

- add first_name, last_name and membership to column list and make the memebership editable 
and 
- order the list first by first_name then last_name


___Solution___

```python
@admin.register(Customer)
class CustomerAdmin(admin.ModelAdmin):
    list_display = ['first_name', 'last_name', 'membership']
    list_editable = ['membership']
    list_per_page = 15
    ordering = ['first_name', 'last_name']
```