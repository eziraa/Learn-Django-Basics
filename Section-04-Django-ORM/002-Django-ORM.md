## Django ORM

- Data in Relational Database stored in the form of table
- To insert data to the database table or to get extract data from the database table we use SQL statement
- But writing SQL statement for all thing manually is a little more difficult 
- To solve this problem django has solution (ORM)
- ORM means as the name indicates it is mapping object to relational database table
- SO in ORM we do not need write SQL code rather we write python code and then django convert it to SQL 

___Example___

```python
product = Product.objects.all()
```

- The above is equivalent to

```sql
select * from store_product
```

- ORM provide efficient code for complex query

___Importance of ORM___

_1. Reduce complexity_

_2. Make our code more understandable_

_3. get more done in less time(less code more job less time)_

___Example___

- Let us see how migration work
- First we write python class called `model`
- Then we make migration
- Finally we apply the migration
- When we apply the migrations it execute the equivalent SQL code of the migration on the database
- It will do like
    1. _create database_
    2. _create table_
    3. _drop database_
    4. _drop table_
    5. _insert data_
    6. _query SQL query_
    7. _delete some instance_
    8. _update table_