## Annotating Objects

- Annotating means adding additional field name to the result of query set
- We can do this by unsing annotate method

___Example___

```python

products = Product.objects.annotate(is_new = True)

```
- We can add annotate like the above but there is a problem in the above code the value of the new field name must be instance of Expression class
- So the field value can not be simple boolean value or str or number
- So what is Expression class
- Expression class contain the following child class
    - _Value_ -> for simple boolean or str or numbr value
    - _F_ -> for field of the model
    - _Func_ -> to call database function
    - Aggregate -> for Sum, Count, Min, Max, Avg

___Let us modify the above code as follows by wrapping the value with `Value` class___

```python
products = Product.objects.annotate(is_new = Value(True))

