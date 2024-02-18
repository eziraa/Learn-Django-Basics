## Deffering Fields

- As we have seen before we can use values or value_list methods to optimize our code 
- But in those method the query return only the provided fields 
- If we want access other than the provided fields we got no thing
- We can use `only` method to do this
- In this method first it return instances with the provided fields only then when we try to access other than those fields it will send other query to the database
