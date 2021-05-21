---
title: Python
tags: language
---

## 
> Python is the most powerful language you can still read.
> \
> \- Paul Dubois
## **Language**
#### ^^Setup^^
### ^^Resources^^
#### TODO [Comprehensive Cheatsheet](https://github.com/gto76/python-cheatsheet)
:PROPERTIES:
:todo: 1620885582093
:END:
#### TODO [article on logging for a python app](https://towardsdatascience.com/the-reusable-python-logging-template-for-all-your-data-science-apps-551697c8540)
:PROPERTIES:
:todo: 1620885579117
:END:
#### TODO [thomas-cokelaer python notes](https://thomas-cokelaer.info/tutorials/python/index.html)
:PROPERTIES:
:todo: 1620885575348
:END:
#### TODO [perceptilabs](https://www.perceptilabs.com/papers)
:PROPERTIES:
:todo: 1620885568483
:END:
### ^^Projects^^
### ^^Tools^^
#### [[Jupyter]]
#### [[Kite]]
#### **Dependency Management** [[Python Poetry]] [[pydeps]]
####
### ^^Libraries^^
#### **Utils:** [[pyinstaller]], [[os]]
#### **Documentation:** [[pydoc]]
#### **Benchmarking:** [[clockpy]]
#### **Unit Testing:** [[unittest]]
#### **Logging:** [[logging]]
#### **Virtual Environment:** [[venv]]
#### **File System:**
##### **File System Monitoring:** [[watchdog]]
#### **GUI Apps:**
##### **tkinter:** [[tkinter]], [[tkcalendar]]
#### **Data Science:**
##### **Data Manipulation:** [[pandas]], [[datetime]]
##### **Data Visualization:** [[matplotlib]]
### ^^Syntax^^
#### **Conventions**
##### TODO check PEP for style conventions
:PROPERTIES:
:todo: 1620898933798
:END:
##### Use uppercase initials for class names, lowercase for all others.
###### function names all in lowercase
###### `class.object.field` names should not be capitalized, and if multiple words used, then separate with underscores:
####### `user1.first_name` > `user1.firstName`
##### Name a private identifier with a leading underscore ( `_username`)
##### Name a strongly private identifier with two leading underscores (`__password`)
##### Special identifiers in Python end with two leading underscores.
###### _A.K.A. Dunder methods (double under-score)_ `__MAIN__`
#### **Decorators**
##### TODO [Decorators 101](https://sureshdsk.dev/python-decorators-101)
:PROPERTIES:
:todo: 1620835767488
:END:
##### TODO [Decorators 201](https://sureshdsk.dev/python-decorators-201)
:PROPERTIES:
:todo: 1620835782488
:END:
##### TODO [Decorators with params](https://sureshdsk.dev/python-decorators-with-parameters)
:PROPERTIES:
:todo: 1620835794488
:END:
### ^^Data Types & Structs^^
### ^^Flow Control^^
#### **Loops**
##### _While Loop_
######
```python
i = 1
while i <= 10:
    print(i)
    i+=1
```
##### _For Loop_
######
```python
for letter in "giraffe academy":
    print(letter)

friends = ["Jim", "Suzy", "Kevin"]

for name in friends:
    print(name)

for index in range(10):
    print(index) # prints 1-9 not including 10 so always increment upwards by 1
```
#### **Exception Handling**
##### 
```python
try:
    number = int(input("enter a number: "))
    print(number/0) #divide by zero
except ZeroDivisionError as err:
    print(err)
    print("Divided By Zero")
except ValueError:
    print("invalid input")
# OUTPUT:
# ./test.py
# enter a number: 1
# integer division or modulo by zero
# Divided By Zero
```
### ^^Functions^^
#### **Functions**
##### 
```python
import math

def area(r):
    """Area of a circle with radius 'r'."""
    return math.pi * (r**2)
```
#### **Map Filter Reduce**
##### 
```python
import math

def area(r):
    """Area of a circle with radius 'r'."""
    return math.pi * (r**2)

radii = [2, 5, 7.1, 0.3, 10]

# Method 1: Direct Method
areas = []
for r in radii:
    a = area(r)
    areas.append(a)

print(areas)

# Method 2: MAP Function
# map(<function>, <list, tuple, or other iterable object>)
list(map(area, radii))
print(list(map(area, radii)))

# Celcius to Farenheit with map and lambda
temps = [("Berlin",29), ("Cairo", 36), ("Buenos Aires", 19), ("Los Angelas", 26), ("Tokyo", 27), ("New York", 28), ("London", 22), ("Beijing", 32)]

c_to_f = lambda data: (data[0], (9/5)*data[1] + 32)

print(list(map(c_to_f, temps)))

# FILTER
import statistics

data = [1.3, 2.7, 0.8, 4.1, 4.3, -0.1]
avg = statistics.mean(data)
print(avg)
print(list(filter(lambda x: x > avg, data)))

# Remove Missing Data
countries = ["", "Argentina", "", "Brazil", "Chile", "", "Columbia", "", "Ecuador", "", "", "Venezuela"]

print(list(filter(None, countries)))

# dont use reduce, just use an explicit for loop
```
### ^^Object Oriented Programming^^
####
```python
import datetime

# class names should start with a capital letter
class User:
    """This is a doc string for this python class,
    if you call help(User) this is what will appear
    it will also show you other useful and relevant information
    but it must be encapsulated within 3 sets of double quotes"""

    # init/initializer is basically a constructor, this code runs first every time a new instance of this class is created
    # self is a reference to the newly created object instance
    def __init__(self, full_name, birthday):
        self.name = full_name # getter/setter
        self.birthday = birthday

    # extract first and last names
    name_pieces = full_name.split(" ")
    self.first_name = name_pieces[0]
    self.last_name = name_pieces[-1]

    def age(self):
        """Return the age of the user in years"""
        today = datetime.date(2001, 5, 12)
        yyyy = int(self.birthday[0:4])
        mm = int(self.birthday[4:6])
        dd = int(self.birthday[6:8])
        dob = datetime.date(yyyy, mm, dd) # date of birth
        age_in_days = (today - dob).days
        age_in_years = age_in_days / 365
        return int(age_in_years)

user1 = new User("john legend", 20191120)
user1.name # result: "john legend"
user1.first_name # result: "john"
user1.last_name # result: "legend"
user1.birthday # result: 20191120

```
#### 
```python
class User1:
    pass

# Conventions: Class names Proper case
# Method names lower case snake case
# variables lower case
user1 = User1()
user1.first_name = "Bryan"
user1.last_name = "Jenks"
user1.age = 27
print(user1.first_name)
print(user1.last_name)

user2 = User1()
user2.first_name = "Frank"
user2.last_name = "Poole"
user2.favorite_book = "2001: A Space Odessey"

# CLASS BENEFITS:
## Methods
## Initialization
## Help Text
import datetime

class User:
    """
    A member of friendface. for now we only store name and birthday, but in the future we will store an uncomfortable amount of information of the user.
    """
    # __INIT__ is the initilization/constructor of the class instance
    def __init__(self, full_name, birthday):
        self.name = full_name
        self.birthday = birthday

        # Extract First and Last Names
        name_pieces = full_name.split(" ")
        self.first_name = name_pieces[0]
        self.last_name = name_pieces[-1]

    def age(self):
        """Return The age of the user in years"""
        today = datetime.date(2001, 5, 12)
        yyyy = int(self.birthday[0:4])
        mm = int(self.birthday[4:6])
        dd = int(self.birthday[6:8])
        dob = datetime.date(yyyy, mm, dd)
        age_in_days = (today - dob).days
        age_in_years = age_in_days / 365
        return int(age_in_years)

user = User("Bryan Jenks", "19920923")
print(user.name)
print(user.first_name)
print(user.last_name)
print(user.birthday)
print(user.age())
```
### ^^File Handling^^
#### 
```python
employee_file = open("employees.txt","r") # Filename, Mode (r:read a:append w:write)
print(employee_file.readable()) # returns T/F if we can read the file
print(employee_file.readline()) # reads the first line of the file
print(employee_file.readline()) # reads the next line (second) in the file
print(employee_file.readline()[2]) # reads the (third) in the file


# always close open files
employee_file.close()
```
### ^^Tips, Tricks, & Hacks^^
#### **Multi-Variable Assignment**
#####
```python
x = 0
y = 0

# can be:
x, y = 0, 0
```
#### **Kwargs**
#####
```python
# Python 3.5+ allows passing multiple sets
# of keyword arguments ("kwargs") to a
# function within a single call, using
# the "**" syntax:

def process_data(a, b, c, d):
   print(a, b, c, d)

x = {'a': 1, 'b': 2}
y = {'c': 3, 'd': 4}

process_data(**x, **y)
# >>> 1 2 3 4

process_data(**x, c=23, d=42)
# >>> 1 2 23 42
```
#### **Default Parameters**
##### 
```python
# In Python 3 you can use a bare "*" asterisk
# in function parameter lists to force the
# caller to use keyword arguments for certain
# parameters:

>>> def f(a, b, *, c='x', d='y', e='z'):
...     return 'Hello'

# To pass the value for c, d, and e you
# will need to explicitly pass it as
# "key=value" named arguments:
>>> f(1, 2, 'p', 'q', 'v')
TypeError:
"f() takes 2 positional arguments but 5 were given"

>>> f(1, 2, c='p', d='q',e='v')
'Hello'
```
## 
---
## **Workflow**
### _Starting_
#### `python3 -m venv projects/env_name`
##### create virtual environment
#### `source project_env/bin/activate`
##### activate virtual environment
#### `which python`
##### confirm usage
#### install necessary packages
#### `pip freeze  requirements.txt`
##### snap shot of requirements for reproduce-ability with
#### `pip install -r requrirements.txt`
##### to import requirements from elsewhere
### _Ending_
#### `deactivate`
##### deactivate virtual environment
