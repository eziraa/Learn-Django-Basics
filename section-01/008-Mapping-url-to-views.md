## Mapping URL to Views

- As we have seen before `views` are request handler
and requests come via URL then we have to mapp a `url` to its views(to handle it and return it response)

- There is one main `urls` module inside our main project 
- This url see the `url` which comes from the request and try to handle and response it but if i can not resolve then it try to forward to other `urls` module of its apps if there is no a view to handle it then it return response with status code (`200`)

- We can create a `urls` module from the `playground` app and then write our mapping in the list of `urlpatterns`

### Let us create our mapping

```python
from django.urls import path
from . import views
urlpatterns = [
    path('', views.say_hello, name='say_hello')
]
```

### Let me explain the above code 
1. First we have to import `path` function from djanago urls and the `views` module from the playground app
2. Then create a list named urlpatterns for mapping the `url` to `view` by path function
3. We can give a name for the mapping for later indication for example for redirecting and reversing we will see later