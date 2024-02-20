## Deferring Fields

- As we have seen before we can use values or value_list methods to optimize our code 
- But in those method the query return only the provided fields 
- If we want access other than the provided fields we got no thing
- We can use `only` method to do this
- In this method first it return instances with the provided fields only then when we try to access other than those fields it will send other query to the database

___Example___
```python
products = Product.objects.only('id', 'title')
```
- First it  return an instance with field value id and title then If we try to access 'unit_price' it will query to the database to get the unit price
- This not optimization be careful because if your first query contain 1000000 instance then it will query to the database 1000000 times 

___Defer method___
- We can use other method called `defer` to defer unwanted fields later 
- Then it exclude fields we deffer

___Example___

```python

products = Product.objects.defer('description')

# It will return a bunch of queryset instance with their fields other than the description
```