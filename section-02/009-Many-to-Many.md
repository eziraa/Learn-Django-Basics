## Many to Many Relationship

- This type of relationship is to indicate one instance of a model relate to many instance of the other model and the reverse is True

___Example___

 In our E-commerse project
1. Order - Product
    one order will containe different Products
    one product will inlcuded in different orders

- To implement it we need Association class because the relation create additional attribute called quantity
- So we have to create OrderItem Association class

```python

class OrderItem (models.Model):
    order = models.ForeignKey(Order, on_delete=models.PROTECT)
    product = models.ForeignKey(Product, on_delete=models.PROTECT)
    quantity = models.PositiveSmallIntegerField()
    unit_price = models.DecimalField(max_digits=6, decimal_places=2)

```

2. Cart - Product

- To implement cart to product relationship first we have to create Cart model

```python
class Cart(models.Model):
    created_at = models.DateTimeField(auto_now_add=True)
```

- Cart and product have many to many relation ship so and the relation create additional relation ship
- So we need an other association class
- This class also known as `CartItem` 

```python
class CartItem(models.Model):
    product = models.ForeignKey(Product, on_delete=models.CASCADE)
    cart = models.ForeignKey(Cart, on_delete=models.CASCADE)
    quantity = models.PositiveSmallIntegerField()
```