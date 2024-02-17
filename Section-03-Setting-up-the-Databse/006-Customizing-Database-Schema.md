## Customizing Database Schema

- We can customize our database schema by add inner class called `Meta` inside the model

___Example__

```python

class Animal(models.Model)
    #  some fields goes here
    name = models.CharField(max_length = 255)
    class Meta:
        db_table = 'tbl_animal'
```
- The above code will change the table name to tbl_animal rather `<app name>_Animal`