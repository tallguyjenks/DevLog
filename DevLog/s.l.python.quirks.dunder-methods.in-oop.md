---
id: x1pe7g0d0wgazcl4oemzoy4
title: In Oop
desc: ''
updated: 1641496601571
created: 1641421830492
---


### In OOP Code

> items can have their operations, `__add__` == `( + )` have their operations of arithmatic assignments `__iadd__` == `( += )` and If one of those methods does not support the operation with the supplied arguments, it should return `NotImplemented` == `__radd__`.

- `__add__` == `( + )` [[s.l.python.quirks.dunder-methods.in-oop.__add__]]
- `__sub__` == `( - )`
- `__mul__` == `( * )`
- `__matmul__` == `( @ )`
- `__truediv__` == `( \ )`
- `__floordiv__` == `( \\ )`
- `__mod__` == `( % )`
- `__divmod__` == `divmod()`
- `__pow__` == `( ** )`
- `__lshift__` == `( << )`
- `__rshift__` == `( >> )`
- `__and__` == `( & )`
- `__xor__` == `( ^ )`
- `__or__` == `( | )`
- `__lt__` == `( < )`
- `__le__` == `( <= )`
- `__eq__` == `( == )`
- `__ne__` == `( != )`
- `__gt__` == `( > )`
- `__ge__` == `( >= )`
- `__neg__` == `( - )`
- `__pos__` == `( + )`
- `__abs__` == `abs()`
- `__invert__` == `( ~ )`
- `__complex__` == `complex()`
- `__int__` == `int()`
- `__float__` == `float()`
- `__index__` [https://docs.python.org/3/reference/datamodel.html#object.\_\_index\_\_](https://docs.python.org/3/reference/datamodel.html#object.__index__)
- `__round__` == `round()`
- `__trunc__` == `math.trunc()`
- `__floor__` == `math.floor()`
- `__ceil__` == `math.ceil()`
- [[s.l.python.quirks.dunder-methods.in-oop.dictionary-dunders]]
  - `__setitem__` When assigning values in a dictionary
  - `__getitem__` Executed when we run the `dict['key']` type of operation
  - `__delitem__` ran when deleting a dictionary value `del dict['key']`
  - `__contains__` Executed when we run the `in` operator `if item in class_instance:`
  - `__len__` Is called if we ran a `len()` operation on our class instance 
- `__call__` if `instance = Class()` then `__call__` is ran when we do: `instance()` right after
- `__init__` init function is run as soon as a class instance is generated. It's the constructor.
- `__post_init__` used in [[s.l.python.oop.data-classes]] for after `__init__` as thats overwritten by data class
- `__getattr__` Called when the default attribute access fails with an AttributeError
- `__getattribute__` Called unconditionally to implement attribute accesses for instances of the class. 
  - If the class also defines `__getattr__()`, the latter will not be called unless 
    - `__getattribute__()` either calls it explicitly or raises an AttributeError.
- `__setattr__` Called when an attribute assignment is attempted. 
  - This is called instead of the normal mechanism (i.e. store the value in the instance dictionary).
- `__delattr__` Like `__setattr__()` but for attribute deletion instead of assignment. 
  - This should only be implemented if `del obj.name` is meaningful for the object.
- `__dir__` Called when `dir()` is called on the object. A sequence must be returned. 
  - dir() converts the returned sequence to a list and sorts it.
- `__format__` when the class is being formatted in an fstring for with `.format()`
- `__bool__` [https://docs.python.org/3/reference/datamodel.html#object.\_\_bool\_\_](https://docs.python.org/3/reference/datamodel.html#object.__bool__)
- `__del__` The destructor of the class and what runs when attempting to `del instance`
- `__bytes__` Computes a byte-string representation of an object. This should return a bytes object.
- `__format__` produces a ???formatted??? string representation of an object.
- `__hash__` [https://docs.python.org/3/reference/datamodel.html#object.\_\_hash\_\_](https://docs.python.org/3/reference/datamodel.html#object.__hash__)
- `__repr__` Returns a representation of an object instance as a string [[s.l.python.quirks.dunder-methods.in-oop.__repr__]]
- `__str__` when not defined it calls `__repr__` by default to represent the instance as a string [[s.l.python.quirks.dunder-methods.in-oop.__str__]]
- `__unicode__` New preferred method compared to `__str__` in python 2
  - Python 3 uses unicode and therefore defaults to the `__str__` method 
- `__enter__` Enter the runtime context related to this object using the `with` statement
- `__exit__` Exit the runtime context related to this object
- `__reversed__` not used with slice `[::-1]` but rather with `reversed()`
- `__slots__` <https://medium.com/@stephenjayakar/a-quick-dive-into-pythons-slots-72cdc2d334e>
