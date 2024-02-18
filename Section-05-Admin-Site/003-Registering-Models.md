## Registering Models in admin site

- To manage models in admin site we have to register those models first 

- We can register models in admin module of the app

- For example we can register models of store app as follows

```python
from django.contrib import admin
list_of_models = [Collection, Order, OrderItem, Customer, Product, Promotion]

admin.site.register(list_of_models)
```
- `register` method can take single model or iterable

- We will see the following
![registred models](../Images/registered%20models.png)

- Let us look up Product model by click on it

- We will get the following

![product model](../Images/Product%20model.png)

- We can change str representation of the model to make it more expressible

- Let us change it in its orginal model class

```python
class Product(models.Model):
    title = models.CharField(max_length=255)
    description = models.TextField()
    slug = models.SlugField(default='-')
    unit_price = models.DecimalField(max_digits=6, decimal_places=2)
    inventory = models.IntegerField()
    last_update = models.DateTimeField(auto_now=True)
    collection = models.ForeignKey(Collection, on_delete=models.PROTECT)
    promotions = models.ManyToManyField(Promotion, related_name='products')

    # simply add this method
    def __str__(self):
        return self.title
```


