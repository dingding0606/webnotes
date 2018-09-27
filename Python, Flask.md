# Python

### Rounded value

`print(f"{1/10:.30f}")`

return: 0.100000000000000005551115123126

WHY?

https://www.exploringbinary.com/why-0-point-1-does-not-exist-in-floating-point/



### Set

```python
inventory = set()
while True:
    item = input("Item: ")
    if not item:
        break
    inventory.add(item)

# Report inventory
for item in sorted(inventory):
    print(item)
```

Set: one value can only occur one time

if entered a same value for multiple times, there is only one exists.



### Dictionary

```python
inventory = {}
while True:
    item = input("Item: ")
    if not item:
        break
    if item in inventory:
        inventory[item] += 1
    else:
        inventory[item] = 1  # dict[key]: returns value

# Report inventory
for key, value in inventory.items():  # get the pair 
    print(f"{key}: {value}")
```

`dict.items()`: Return a **copy** of the dictionary’s list of (key, value) pairs.

```python
>>> dic = {"foo":1, "bar":2, "baz":3}
>>> dic
{'foo': 1, 'bar': 2, 'baz': 3}
>>> dic.items()
dict_items([('foo', 1), ('bar', 2), ('baz', 3)])
```





# Flask Framework: for web development

Flask used jinja2 to solve the templating problem: {{% xxx % }}



```html
<!DOCTYPE html>

<html>

    <head>

        <meta name="viewport" content="initial-scale=1, width=device-width"/>

        <title>froshims0</title>

    </head>

    <body>

        {% block body %} you could have a default, but will be over rided{% endblock %}

    </body>

</html>
```



### Block Inheritance

```html
{% block body %}{% endblock%}
```

"body" can be "content" or any word



### Send Email Using Code

```python
import os
import smtplib

server = smtplib.STP("smtp.gmail.com", 587)  # gmail use port 587
server.starttls()
server.login("jharvard@cs50.net", os.getenv("PASSWORD"))
server.sendmail("jharvard@cs50.net", email, message)
```
