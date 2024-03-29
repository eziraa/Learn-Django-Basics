## Transactions

- All transactions needs to be executed in atomic way
- Meaning to be executed all together if one of the transaction failed rollback all

___Example___
```python
order = Order()
order.customer_id = 1
order.save()

item = OrderItem()
item,order = order
item.product_id = 1
item.quantity = 3
item.unit_price = 23
item.save()

```
- In the above we will create order and item but what id after we created an order some thing happened and we can not create item

- Order with out orderitem does not make sense

- To solve this we use `Transaction`
- If if we make those two operation in one transaction then all of them executed only there is no error on any of them 
- If any error happened on any of them the operation will be rolled back

___Let us update the above code by making it under atomic function decorator

```python
from django.db import transaction

@transaction.atomic()
def index(request):
    order = Order()
    order.customer_id = 1
    order.save()

    item = OrderItem()
    item,order = order
    item.product_id = 1
    item.quantity = 3
    item.unit_price = 23
    item.save()

```
- We can write as above the decorator if all of code needs to be under transaction

- But if there are some code needs not to be under transaction we can use `with` as context manger

___Example___

```python
def index(request):
    # some code outside the transaction
    with transaction.atomic():
        order = Order()
        order.customer_id = 1
        order.save()

        item = OrderItem()
        item,order = order
        item.product_id = 1
        item.quantity = 3
        item.unit_price = 23
        item.save()

```

