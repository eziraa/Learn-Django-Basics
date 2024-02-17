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

- We call the above relationships as indirect `many-to-many` relationship

- There a true many-to-many relationship

___Exmple___

    - this is between Product and Promotion models
    - A product will have diffent promotion and
    - A promotion will include defferent products
___Let us implement it___

- First create Promotion model

```python

# create Promotion model
class Promotion(models.Model):
    description = models.CharField(max_length=255)
    discount = models.FloatField()
```
- Then add the relationship

```python

# create Promotion model
class Promotion(models.Model):
    description = models.CharField(max_length=255)
    discount = models.FloatField()
    products = models.ManyToManyField(Product, related_name='promotions')
```

- After we create this relationship django create the reverse relationship and it will create a field called `promotions` which we gave in the paramater called `related_name`  in the above relation

- But if we did not give  related name then it automatically create field named `product_set`
- Then we can access promotions for particular product like (product.promotions or product.promotion_set)
