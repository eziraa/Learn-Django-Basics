## Building Data Model

- Let use build data model for our E-Commerce Project

- Let us begin with two models Product and Cart
    - A Product will be in many carts and
    - A Cart will contain many products so we can say they have many-to-many relationship 
    - And when those class related each other they create a special attribute called '`quantity`' 
    - This attribute indicates the number of products in the cart

    - So we have to create other model because of this attribute called `CartItem` model between `Product` and `Cart` model
    - This class(model) also known as `Association` Class
- Model `Customer` and `Order`
    - Those two models will have one to many relationship
- Model `Order` and `Product`
    - Those two classes have many-to-many relationship
    - One product will be in different orders and one order contain different products
    - And their relationship creates attribute called `quantity`
    - Then we have to create Association class called `OrderItem`
- Model Product and Tag
    - Those two models will have many-to-many relationship
    - A product will be tagged by different tags and a tag will be reverenced by different tags
    - So we have to create Association class called `TaggedItem` between those two models
