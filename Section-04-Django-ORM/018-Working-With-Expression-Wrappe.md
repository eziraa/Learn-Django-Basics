## Working with Expression Wrapper

- `ExpressionWrapper` used for complex expression

___Example___

```python
from django.db.models import F
products = Products.objects.annotate(
    discounted_price = F('unit_price') * 0.8
)

```
- The above expression has an error of mixing expression type because `unit_price` has field type of DecimalField and `0.8` is FloatField

- To solve this problem we have to set output_field (data type after the expression evaluated) and to  set output_field we use `ExpressionWrapper` class

- We can use as follows

```python

from django.db.models import ExpressionWrapper

discounted_price = ExpressionWrapper(F('unit_price') * 0.8, output_field = DecimalField)
products = Product.objects.annotate(
    discounted_price = discounted_price
)

```
This will add addtional column name called `discounted_price`