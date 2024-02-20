## One to Many Relationship

- We can update the above Address model for one_to-one relationship

___Let us update is___

```python
class Address(models.Model):
    street = models.CharField(max_length = 255)
    city = models.CharField(max_length = 255)
    customer = models.ForeignKey(Customer, on_delete = models.CASCADE)
```

- The above indicates that one customer will have many address

___Let us create One to Many relationship___ 

1. Between Product and Collection

```python
class Collection(models.Model):
    title = models.CharField(max_length=255)

# create Product model
class Product(models.Model):
    title = models.CharField(max_length=255)
    description = models.TextField()
    price = models.DecimalField(max_digits=6, decimal_places=2)
    inventory = models.IntegerField()
    last_update = models.DateTimeField(auto_now=True)
    collection = models.ForeignKey(Collection, on_delete=models.PROTECT)
```
2. Between Customer and Order

```python

class Customer(models.Model):
    MEMBERSHIP_BRONZE = 'B'
    MEMBERSHIP_SILVER = 'S'
    MEMBERSHIP_GOLD = 'G'
    MEMBERSHIP_CHOICES = [
        (MEMBERSHIP_BRONZE, 'Bronze')
        (MEMBERSHIP_SILVER, 'Silver')
        (MEMBERSHIP_GOLD, 'Gold')
    ]
    first_name = models.CharField(max_length=255)
    last_name = models.CharField(max_length=255)
    email = models.EmailField(unique=True, primary_key=True)
    phone_number = models.CharField(max_length=255)
    birth_date = models.DateField(null=True)
    membership = models.CharField(
        max_length=1, choices=MEMBERSHIP_CHOICES, default=MEMBERSHIP_BRONZE)
    address = models.ForeignKey(Address, on_delete=models.SET_NULL, null=True)

# Create Order Class
class Order(models.Model):
    PAYMENT_STATUS_PENDING = 'P'
    PAYMENT_STATUS_COMPLETED = 'C'
    PAYMENT_STATUS_FAILED = 'F'

    PAYMENT_STATUS_CHOICES = [
        (PAYMENT_STATUS_PENDING, 'Pending'),
        (PAYMENT_STATUS_COMPLETED, 'Completed'),
        (PAYMENT_STATUS_FAILED, 'Failed'),
    ]

    placed_at = models.DateTimeField(auto_now_add=True)
    payment_status = models.CharField(
        max_length=1, choices=PAYMENT_STATUS_CHOICES, default=PAYMENT_STATUS_PENDING)
    customer = models.ForeignKey(Customer, on_delete=models.PROTECT)

```

