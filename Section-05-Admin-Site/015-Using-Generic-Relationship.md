## Using Generic Relationship

- As we  have seen before generic relationship when relation it between two apps model and to make the apps not depend each other made the relationship generic 

- So how to manage children in generic relationship

___Let us see the relationship between Tag and Product___

- We manage the child (Tag) by creating a class which inherits `GenericTabularInline`

- To create this first import the TaggedItem and `GenericTabularInline`  from `django.contrib.contentTypes.admin`

- Let us create the generic inline class

```python
class TagInline(GenericTabularInline):
    model = TaggedItem

```

- Then add this inline class to ProductAdmin class `inlines` list

```python
class ProductAdmin(admin.ModelAdmin):
    # some code goes here
    inlines = [TaggedInline]
```

- after this time we can add tags when we create new product

- We can also add convert the dropdown list of tags to `auto_completed_fields`


```python
class TagInline(GenericTabularInline):
    auto_completed_fields = ['tag']
    model = TaggedItem

```
- But make sure the you are change the str representation of the Tag model to the label and add it to search_fields list in TagAdmin class 

- Let us do it

from tags.model module do the following to change str representation

```python

class Tag(models.Model):
    # other code goes here  
    def __str__(self):
        return self.label
```

from tags.admin module do the following to add the label to search_fields list

```python
@admin.register(Tag)
class TagAdmin(admin.ModelAdmin):
    search_fields = ['label']

```
