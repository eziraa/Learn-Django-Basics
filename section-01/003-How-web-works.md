## How web works

- We can see web by dividing to front end and back end
- Front end contains actions to performed on client machine or broweser
- Back end contains activies to be performed in web server
to validate , proccess client request and return correct response to the client
- Back end and front end connected by request and the request contains URL(Uniforma resourse locator)
-As the name indicates URL used to locate a resource on the internet
- The resource can be 
    - Page
    - Image
    - Video
    - PDF
- To send request and get response web uses HTTP protocol
- HTTP protocol defines how client and server communicate each other
- We can set different end points on the server to different catagories
- Exmple
    - /products -> To get a list of products
    - /orders -> To get a list of orders
    - /customers -> To get lsit of customers
- The combination of all the above endpoints give an interface between client and server 
- We call this as API
- We will build an API for online store and clients can save their data by using this API
- After we finished this API we can build the front end by using React or vue or other and use this API as a back end
