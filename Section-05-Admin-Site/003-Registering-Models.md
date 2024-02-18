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


