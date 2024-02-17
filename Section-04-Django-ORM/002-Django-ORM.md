## Djnngo ORM

- Data in Relational Database stored in the form of table
- To insert data to the database table or to get extract data from the database table we use SQL statment
- But writing SQL statment for allthing manually is a little more difficult 
- To solve this problem django has solution (ORM)
- ORM means as the name indicates it is mapping object to ralational database table
- SO in ORM we do not need write SQL code rather we write python code and then django convert it to SQL 

___Example___

```python
product = Product.objects.all()
```

- The above is equivalent to

```sql
select * from store_product
```

- ORM provide eficient code for complex query

___Importance of ORM___

_1. Reduce complexity_

_2. Make our code more understandable_

_3. get more done in less time(less code more job less time)_
