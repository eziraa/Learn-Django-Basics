## Building Data Model

- Let use build data model for our E-commerse Project

- Let us begin with two models Product and Cart
    - A Product will be in many carts and
    - A Cart will contain many products so we can say they have many-to-many relationship 
    - And when those class related each other they create a spetial attribute called '`quantity`' 
    - This attribute indicates the number of products in the cart

    - So we have to create other model because of this attribute called `CartItem` model between `Product` and `Cart` model
    - This class(model) also known as `Association` Class