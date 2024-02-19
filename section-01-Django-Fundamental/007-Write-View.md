## Write View

- View is a function that takes a `request` and return a `reponse`
- It is a `request` handler

 ___Let us write a view inside the playgound app___

In real Project when we write a view we will do the following things

- Pull data from database
- Save data to database
- Transform data
- Send Email

- But as biggineer let us write a view called `say_hello` that return simple HttpReponse by importing `HttpResponse` class from `django.http` module

```python
from django.http import HttpResponse

def say_hello(request):
    return HttpResponse('Hello Everyone')

```
