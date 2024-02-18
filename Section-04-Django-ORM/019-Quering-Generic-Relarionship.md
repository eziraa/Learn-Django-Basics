## Quering Generic Relationship

- As we have seen before Generic relation ship means a relationship between to models which are found in diffrent model
- As the term  Generic indicates  that the relationship oneside (one model known) but the other side is generic means can be any model
- It used to reduse coupling
- In our model designing  TaggedItem has a generic relation ship  between Product model but we can change as follows

    - ___TaggedItem <---> Product___
    - ___TaggedItem <---> Article___
    - ___TaggedItem <---> Video___
    - ___TaggedItem <---> News___

- Generic relation ship is done via `ContentType` class because this class has allover control on all models in the project

- So to make quering generic relationship we have to get the three neccessary things

1. _content type_ -> model in the other side
2. _object id_ -> specific object id  on the model
3. _content object_ -> the specific object 

___Getting content type___

- To get the content type we use `get_for_model` in `ContentType` manager

_for example for product_

```python
from django.contrib.contenttypes.models import ContentType
 content_type = ContentType.objects.get_for_model(Product)
taggeditems = TaggeItem.objects\
        .select_related('tag')\
        .filter(
            content_type=content_type,
            object_id=1
        )
```