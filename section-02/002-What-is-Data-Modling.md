## Data modeling

- Model Represent the Database Table
- For exmaple for our E-commerse app we will have the following models
    1. _Product_
    2. _Collection_
    3. _Customer_
    4. _Order_
    5. _Tag_

- And there will be a relationship between those models

___There are three types of model relation ship___

1. ___One To One Relationship___

    - This relationship indicates that an instance of a model will relate only one instance of the other model

    ___Example___

    _User and Telegram account through one phone number_

        - A User will has only one telegram account through one phone number

        - And One telegram account will be managed by one telegram user only
    2. ___One to Many Relationship___
        - One to many relationship is when the instance of a model in relate to many instance of other model

        __Example__

            In Our project we have `Order` and `Customer` model

            These two model relates in one to many relationship 

            A customer will have many orders but an order can be ordered by one customer
    
    3. ___Many to Many Relationship___

        - This type of relationship is when one instance of a model related to many instance of other model
        - And the reverse is `True`

        __Example__

            A collection will contain different products and a product will be in many defferent collections

- Models will have different Attributes

__Exmaple__
    
    Product Model Will have the following attributes
    - title
    - description
    - price 
    - inventory

    Collection Will Have the following attributes
    - title
    - featured_product
