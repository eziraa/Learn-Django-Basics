## Managers and Querysets

- Every model has manger it return an API for interaction between the model class and the databas
- Through this API you can 
    -  _Get data_
    - _Filter dara_
    - _Group data_
    - _Sort data_

- For example `product` model has `Product` manager
- This return Product.objects API to fo the above things

___QuerySet___

- Query Set is an object returned by the API when we make the above opreration
- Let us update say_hello function of views module in playground app
- Change its name to index and try to get all products from the database through product manager

```python
from django.shortcuts import render
from django.http import HttpResponse
from store.models import Product

def index(request):
    querySet = Product.objects.all()
    return render(request, 'index.html', {'name': 'Ezira'})
```
- Variable querSet store a set of query retrived from the database table 

- Let us send the query set to the template file as context
- To send let us cast to list for simplicity
- To cast to list simply wrap with keyword `list`
- Then add to the context mapping object as `products`

__let us modify the above method__

```python
from django.shortcuts import render
from django.http import HttpResponse
from store.models import Product

def index(request):
    # accessing the product objects through queryset
    querySet = Product.objects.all()
    # Casting querySet to list
    querySetList = list(querySet)
    return render(request, 'index.html', {'name': 'Ezira',
    'products':querySetList })
```
