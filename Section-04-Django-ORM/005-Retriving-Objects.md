## Retriving Objects

- To retrive objects from database we can use the following methods

___Example___
- To retrive all objects of the model use `all` method


```python
productQuerySet = Product.objects.all()
```
- To retrive an object you can use `get`method
- When we use `get` it return the actual object not query set

```python
product = Product.objects.get(id = 1)
```
- You can also use `pk` instead of `id` to indicate primary key of the table
- When we use pk in django transform pk to the name of the primary key

```python
product = Product.objects.get(pk = 1)
```

___Remember___
- What if we give an id which does not exist

- It will raise object does not exist exception
- To fix this import ObjectDoesNotExist exception and write it with `try` block as follows

```python
from django.shortcuts import render
from django.http import HttpResponse
from store.models import Product
from django.core.exceptions import ObjectDoesNotExist

def index(request):
    try:
        product = Product.objects.get(pk=0)
    except ObjectDoesNotExist:
        return HttpResponse("<h1> Object does not exist </h1")
    return render(request, 'index.html', {
        'name': 'Ezira',
        'products': list([product])})
```
