

-  [[s.l.python]]
	- the `__main__` function is used so that when you import the script as a module it will not execute the code within it, rather it will now let you import the code as a module so I can `from <module> import <something>` The only time the that `__name__ == __main__` is when we run the file as a script
-  [[s.l.python]] [5 Things You're Doing Wrong When Programming in Python](https://www.youtube.com/watch?v=fMRzuwlqfzs&ab_channel=JackofSome)
	-  [[s.l.python]] [Python Decorators in 15 Minutes](https://www.youtube.com/watch?v=r7Dtus7N4pI&ab_channel=Kite)
	-  [[s.l.python]] [Make Python code 1000x Faster with Numba](https://www.youtube.com/watch?v=x58W9A2lnQc&ab_channel=JackofSome)
	-  [[s.l.python]] the `_` in python can hold the last value in an interactive shell session but can be used like the unnamed register in [[cli.cmd.vim]] and you can use it to avoid issues when unpacking tuples or just throwing something away:

```python
my_tuple = (1,2,3)
x, _, z = my_tuple # (1,2,3)
#> x = 1
#> _ = 2
#> z = 3
```

-  [[s.l.python]] [thomas-cokelaer python notes](https://thomas-cokelaer.info/tutorials/python/index.html)
      [[s.l.python]] [Operator Overloading](https://www.programiz.com/python-programming/operator-overloading)
  b95d08-0498-4303-abb4-02cad357e380
   -  [[s.l.python]] [[s.l.python.libs.rich.inspect]] module and [[s.df.xml]] module [Socratica -- XML & ElementTree || Python Tutorial || Learn Python Programming](https://youtu.be/j0xr0-IAqyk)

```python
import xml.etree.ElementTree as ET
from inspect import getmembers, isclass, isfunction 

# Display classes in ET module
for (name, member) in getmembers(ET, isclass):
if not name.startswith("_"):
	print( name)
```
