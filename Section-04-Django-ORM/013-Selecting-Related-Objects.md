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
This will cause for extra query