## Editing Children using inlines

- We can edit children by usiing inline
- First create inlined children class then add this class to the `inlines` list of the parent class

- If we want to add new order then we get the following page.

![Order  page](../Images/order%20page.png)

- But what if we want to add order item obejcs also 
- Solution is use inlined class
___Example___

- Let us add inline order item class to order class as  follows

_Let use create inlined class which inherits `admin.TabularInline` or `StackedInline`_

```python

class OrderItemInline(admin.TabularInline):
    model = OrderItem

```

_Then let us create OrderAdmin class which inherits `admin.ModelAdmin`_

```python

class OrderAdmin(admin.ModelAdmin):
    list_display = ['id', 'placed_at', 'customer']
```
_Then let us added the inlined class to OrderAdmin `inlines` list_

```python

class OrderAdmin(admin.ModelAdmin):
    list_display = ['id', 'placed_at', 'customer']
    inlines = [OrderItemInline]
```
- The we get the following page in which we can edit children class also

![edit children also](../Images/adding%20children.png)


