## Choices Fields

- When we create a model but the model have attribute with values among some well known things
- Then can use `choices` for this field

___Let us add membership attribute to customer class but its value is among(Bronze, Silver, Gold)___
- This can be done using choices parameter
- The parameter takes value = `list of tuple`

```Python
class Customer(models.Model):

    MEMBERSHIP_CHOICES = [
        ('B', 'Bronze')
        ('S', 'Silver')
        ('G', 'Gold')
    ]
    first_name = models.CharField(max_length =255)
    last_name = models.CharField(max_length = 255)
    email = models.EmailField(unique = True, primary_key = True)
    phone_number = models.CharField(max_length = 255)
    birth_date = models.DateField(null = True)
    membership = models.CharField(max_length = 1, choices = MEMBERSHIP_CHOICES)
```

___Let us to reduce error if we update this late we can add the membership choices as follows___

```Python
class Customer(models.Model):

    MEMBERSHIP_BRONZE = 'B'
    MEMBERSHIP_SILVER = 'S'
    MEMBERSHIP_GOLD = 'G'
    MEMBERSHIP_CHOICES = [
        (MEMBERSHIP_BRONZE, 'Bronze')
        (MEMBERSHIP_SILVER, 'Silver')
        (MEMBERSHIP_GOLD, 'Gold')
    ]
    first_name = models.CharField(max_length =255)
    last_name = models.CharField(max_length = 255)
    email = models.EmailField(unique = True, primary_key = True)
    phone_number = models.CharField(max_length = 255)
    birth_date = models.DateField(null = True)
    membership = models.CharField(max_length = 1, choices = MEMBERSHIP_CHOICES, default = MEMBERSHIP_BRONZE)
```

___Let us create other model called Order with attribute placed_at (auto_populated) and payment_status(pending , complete, failed)___

```python

class Order (models.Model):
    PAYMENT_COMPLETE = 'C'
    PAYMENT_PENDING = 'P'
    PAYMENT_FAILED = 'F'
    PAYMENT_CHOICES = [
        (PAYMENT_COMPLETE , 'Completed'),
        (PAYMENT_PENDING, 'Pending'),
        (PAYMENT_FAILED, 'Failed')
    ]
    placed_at = models.DateTimeField(auto_now_add = True)
    payment_status = models.CharField(max_length = 1, choices = PAYMENT_CHOICES)
```

    