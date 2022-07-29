

```python
class MyClass:
    x = 0
    y = ""

    def __init__(self, anyNumber, anyString):
        self.x = anyNumber
        self.y = anyString

myObject = MyClass(12345, "Hello")

print(myObject.__str__())
print(myObject.__repr__())
print(myObject)

# >>> <__main__.MyClass object at 0x7f75d994f1f0>
# >>> <__main__.MyClass object at 0x7f75d994f1f0>
# >>> <__main__.MyClass object at 0x7f75d994f1f0>

#==========================================================================#

class MyClass:
    x = 0
    y = ""

    def __init__(self, anyNumber, anyString):
        self.x = anyNumber
        self.y = anyString
    def __str__ (self):
        return 'MyClass(x=' + str(self.x) + ' ,y=' + self.y + ')'
myObject = MyClass(12345, "Hello")

print(myObject.__str__())
print(myObject)
print(str(myObject))
print(myObject.__repr__())

# >>> MyClass(x=12345 ,y=Hello)
# >>> MyClass(x=12345 ,y=Hello)
# >>> MyClass(x=12345 ,y=Hello)
# >>> <__main__.MyClass object at 0x7f8f023ef1f0>

#==========================================================================#

class MyClass:
    x = 0
    y = ""

    def __init__(self, anyNumber, anyString):
        self.x = anyNumber
        self.y = anyString
    def __repr__ (self):
        return 'MyClass(x=' + str(self.x) + ' ,y=' + self.y + ')'
myObject = MyClass(12345, "Hello")

print(myObject.__str__())
print(myObject)
print(str(myObject))
print(myObject.__repr__())

# >>> MyClass(x=12345 ,y=Hello)
# >>> MyClass(x=12345 ,y=Hello)
# >>> MyClass(x=12345 ,y=Hello)
# >>> MyClass(x=12345 ,y=Hello)
```
