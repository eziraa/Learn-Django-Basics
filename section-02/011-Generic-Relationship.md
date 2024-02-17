## Generic relationship

- Generic relationshipp used to solve there are model depedency between two different apps 
- Bacause we create apps in a project the apps should be less coupling(ecternal) with high cohesion(internal)

___Example___

- Relation ship between Tag and Product -> when some tag applied to product

___How to apply it___

1. To make generic relationship first we have to know  `type` on which product type the tag applied

    `content_type` field required
2. To get exact object the tag applied we have to know id of the object

    `object_id` field required
3rd. After we know the type of the object and the exact object id on which the tag applied then we need some field whatever name for example for our case `content_object`  

    `content_object` required


