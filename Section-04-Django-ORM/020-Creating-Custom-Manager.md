## Creating Custom Manager

- As we have see before when quering generic relationship it is ugly writing like that always to solve this we can creat custom manager
- Let us create custom manager for TaggedItem

- We can create it by inheriting Manager Class in tags app 

```python
class TaggedItemManager(models.Manager):
    def get_tags_for(self, obj_type, obj_id):
        content_type = ContentType.get_for_model(obj_type)

        return TaggeItem.objects\
            .select_related('tag')\
            .filter(
                content_type=content_type,
                object_id=obj_id
            )
```