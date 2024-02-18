## Calling Database Function

- We can call database by using `Func` class and passing its argumment and the function we call

- Calling function `CONCAT` to create fullname from first name and last name

```python
from django.db.models import Func
customers = Customer.objects.annotate(full_name = Func('first_name', ' ', 'last_anme', function = 'CONCAT'))

# This will add additional fields called full_name with its value concatination of first_name and last_name
```