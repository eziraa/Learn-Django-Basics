## Templates

- When we handle a request we can return `html` file rather than simple string or number
- So to handle a request we can use template to write the html files and return them to the client based on the request

### Let use create `templates` folder and add `index.html` file inside it in `playground` app
![Tempates](../Images/templates.png)

- write some header in `index.html` file

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Index</title>
</head>
<body>
    <h1>Hello every one</h1>
</body>
</html>
```

- Then update or say_hello fucntion in our views in playground app to return this html file by using `render` function

```python

def say_hello(request):
    return render(request, 'index.html')
```

- Then when we browse with url `http://127.0.0.1:8000/playground/`

- We will get the following
![index.html](../Images/index.png)