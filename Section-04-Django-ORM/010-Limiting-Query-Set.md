## Limiting Query Set

- We can limit Query set by Using array slicing

___Example___

```python
products = Product.objects.order_by('title')[:5]

# It will return the first five products after ordering them by name
```

___Remember___

- Slicing return queryset but we can not any fileration or any chaining after  slicing


