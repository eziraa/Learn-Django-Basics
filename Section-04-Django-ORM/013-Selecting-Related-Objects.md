## Selecting Related Objects

- Database table are related to each other as we have seen before on the relationship section
- If we want to display attribute of related object then this will cause for extra query

___Example___

```python

products = Products.objects.all()

```
And pass this queryset to the template file try to access the related model fields example `Collection` class

```html
{% for product in products %}
<h2> {{product.collection_title}}
{% endfor %}
``` 
- This will cause for extra query
- This is happened because it load only the product table instances not include related model instances
- We can instruct the query to load related table we want 
- To instruct the query we use `select_related` method before getting instances

___Example___

```python
products = Product.objects.select_related('collection').all()
```
- It will load related table Collection also this will prevent the extra quering

- When we use `select_related` method django creates `join` statement between the table to related table

- We can use select_related method when the object has one related object only in the other model

- But when the object is related to many objects of the other model we use `prefetch_related` method

- For example on product may has many promotions so we can use for this `prefetch_related` method

```python

products = Product.objects.prefetch_related('promotions')

```