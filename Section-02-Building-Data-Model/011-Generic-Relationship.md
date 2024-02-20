## Generic relationship

- Generic relationship used to solve there are model dependency between two different apps 
- Because we create apps in a project the apps should be less coupling(external) with high cohesion(internal)

___Example___

- Relation ship between Tag and Product -> when some tag applied to product

___How to apply it___

1. To make generic relationship first we have to know  `type` on which product type the tag applied

    `content_type` field required
2. To get exact object the tag applied we have to know id of the object

    `object_id` field required
3. After we know the type of the object and the exact object id on which the tag applied then we need some field whatever name for example for our case `content_object`  

    `content_object` required

___Let us create `Tag` model and the `TaggedItem` model to make generic relationship inside tags app models module___


```python
from django.db import models
from django.contrib.contenttypes.models import ContentType
from django.contrib.contenttypes.fields import GenericForeignKey
# create tag model


class Tag(models.Model):
    label = models.CharField(max_length=255)


# create TaggedItem model for the generic relationship


class TaggedItem(models.Model):
    tag = models.ForeignKey(Tag, on_delete=models.CASCADE)
    content_type = models.ForeignKey(ContentType, on_delete=models.CASCADE)
    object_id = models.PositiveSmallIntegerField()
    content_object = GenericForeignKey()
```

___Let us add other generic relationship for what user likes what object___

- To add this relationship first create `likes` app

```bash
python manage.py startapp likes
```

- Then import built in `User` model and make the relationship through LikedItem model

```python
from django.contrib.auth.models import User
from django.contrib.contenttypes.models import ContentType
from django.contrib.contenttypes.fields import GenericForeignKey
# create LikedItem model to represent what user likes what product


class LikedItem(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    content_type = models.ForeignKey(ContentType, on_delete=models.CASCADE)
    object_id = models.PositiveSmallIntegerField()
    content_object = GenericForeignKey()
```

