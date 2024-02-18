## Calling Database Function

- We can call database by using `Func` class and passing its argumment and the function we call

- Calling function `CONCAT` to create fullname from first name and last name

```python
from django.db.models import Func
customers = Customer.objects.annotate(full_name = Func(F('first_name'), Value(' '), F('last_name'), function = 'CONCAT'))

# This will add additional fields called full_name with its value concatination of first_name and last_name
```

- We can also use `Concat` instead of calling database functions as follows

```python
from django.db.models.functions
customers = Customer.objects.annotate(full_name = Concat('first_name',Value(' '), 'last_name'))

```

- This will also add additional field called full_name it does not require any wrapping of its string parameter
- This is the best one
- We have wrapped the gap with `Value` to prevent djnago finding a column name with named space(some thing unfamiliar named space 🤣🤣🤣)