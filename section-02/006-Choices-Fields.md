## Choices Fields

- When we create a model but the model have attribute with values among some well known things
- Then can use `choices` for this field

___Let us add membership attribute to customer class but its value is among(Bronze, Silver, Gold)___
- This can be done using choices parameter
- The paramter takes value = `list of tuple`

```Python
class Customer(models.Model):

    MEMBESHIP_CHOICES = [
        ('B', 'Bronze')
        ('S', 'Silver')
        ('G', 'Gold')
    ]
    first_name = models.CharField(max_length =255)
    last_name = models.CharField(max_length = 255)
    email = models.EmailField(unique = True, primary_key = True)
    phone_number = models.Charfield(max_length)
    birth_date = models.DateField(null = True)
    membership = models.CharField(max_length = 1, choices = MEMBESHIP_CHOICES)
```