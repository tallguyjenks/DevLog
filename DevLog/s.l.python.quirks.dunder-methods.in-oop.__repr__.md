---
id: xlccb7ybqmcwrvs12qvz3e0
title: __repr__
desc: ''
updated: 1641422050002
created: 1641422046615
---


```python
# A simple Person class

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __repr__(self):
        rep = 'Person(' + self.name + ',' + str(self.age) + ')'
        return rep


# Let's make a Person object and print the results of repr()

person = Person("John", 20)
print(repr(person))
# >>> Person(John,20)
```
