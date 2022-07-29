
```python
class A:
    def __new__(cls, *args, **kwargs):
        print ('new', cls, args, kwargs)
        return super().__new__(cls)
    def __init__(self, *args, **kwargs):
        print ('init', self, args, kwargs)

x = A()
```

`__new__` allows you to modify immutable types before the object instance is created. `__new__` occurs before `__init__` so things like this are possible:

```python
class Uppercase Tuple(tuple):
    def __new__(cls, iterable):
        upper_iterable = (s.upper() for s in iterable)
        return super().__new__(cls, upper_iterable)
```

Whereas this was not possible because the class object already exists even if the instance doesnt yet exist. the OBJECT is what we're trying to beat to the punch

```python
class Uppercase Tuple(tuple):
    def __init__(self, iterable):
        print (f'init {iterable}')
        for i, arg in enumerate (iterable):
            self[i] = arg. upper()
```
