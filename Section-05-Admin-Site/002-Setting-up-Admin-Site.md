## Setting up Admin Site

- We can access admin site at url `/admin`
- But before that we have to create admin manually
- To create admin manually we can use the following command

```bash
python manage.py createsuperuser 
```
- Then it will ask username, email and password 
- Fill those cerrectly adn don't forget

![Admin creation](../Images/admin.png)

- Then after seccefully created admin you can login to (127.0.0.1/admin)
- Enter you admin's username and password of what you created

- You will get the following page

![Admin homepage](../Images/admin%20hoempage.png)


___Let us change site header and index title___

![Admin homepage](../Images/admin%20hoempag1.png)

- We can change this as follows inside urls module of the main project


```python 
from django.contrib import admin

admin.site.site_header = 'Online store Administration'
admin.site.index_title = 'Admin'
```