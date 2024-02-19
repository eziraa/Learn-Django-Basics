## Organizing Models in Apps

- As we have see before apps are the building blocks of one project
- They used to reduce complexity
- They work in philosophy of `work one thing do it well`
- When we break down projects into multiple apps 
    - the apps should be
        1. Self-contianed
        2. Zero-Coupling
        3. High-Cohesion(focus)
- Let us create two other apps for our project

```bash
python manage.py startapp store
python manage.py startapp tags
```


- Then adding to `INSTALLED_APPS` list in setting module

```python 
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'playground',
    'store',
    'tags',
]
```

- After creating those apps we will have the following project structure

![store snd tags app created](../Images/created%20-%20app.png)