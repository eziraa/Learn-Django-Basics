## Transactions

- All transactions needs to be executed in atomic way
- Meaning to be excecuted all together if one of the transaction failed rallback all

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


