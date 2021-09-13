- **Multi-Variable Assignment**
  collapsed:: true
	-
	  ```python
	  				  				  				  				  				  					  x = 0
	  				  				  				  				  				  					  y = 0
	  				  				  				  				  				  					  
	  				  				  				  				  				  					  # can be:
	  				  				  				  				  				  					  x, y = 0, 0
	  				  				  				  				  				  					  ```
- **Swap Variable Values**
  collapsed:: true
	-
	  ```python
	  				  				  x, y = 1, 0
	  				  				  
	  				  				  ```
- **Kwargs**
  collapsed:: true
	-
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
- **Default Parameters**
  collapsed:: true
	-
	  ```python
	  				  				  # In Python 3 you can use a bare "*" asterisk
	  				  				  # in function parameter lists to force the
	  				  				  # caller to use keyword arguments for certain
	  				  				  # parameters:
	  				  				  				  				  				  					  
	  				  				  def f(a, b, *, c='x', d='y', e='z'):
	  				  				      return 'Hello'
	  				  				  				  				  				  					  
	  				  				  # To pass the value for c, d, and e you
	  				  				  # will need to explicitly pass it as
	  				  				  # "key=value" named arguments:
	  				  				  f(1, 2, 'p', 'q', 'v')
	  				  				  # TypeError: "f() takes 2 positional arguments but 5 were given"
	  				  				  				  				  				  					  
	  				  				  f(1, 2, c='p', d='q',e='v')
	  				  				  'Hello'
	  				  				  ```
- **The \_ in Python**
  collapsed:: true
	- The `_` in python can hold the last value in an interactive shell session but can be used like the unnamed register in [[VIM]] and you can use it to avoid issues when unpacking tuples or just throwing something away:
		-
		  ```python
		  					  					  					  					  my_tuple = (1,2,3)
		  					  					  					  					  x, _, z = my_tuple # (1,2,3)
		  					  					  					  					  #> x = 1
		  					  					  					  					  #> _ = 2
		  					  					  					  					  #> z = 3
		  					  					  					  					  ```
- **Named Tuples**
  collapsed:: true
	-
	  ```python
	  from collections import namedtuple
	  
	  Coordinate = namedtuple("Coordinate", "longitude latitude")
	  location = Coordinate(90, 37.5)
	  print("location:", location) 
	  # accessing attributes with dot notation
	  print(location.longitude, location.latitude) 
	  # Output: 
	  # location: Coordinate(longitude=90, latitude=37.5) 
	  # (90, 37.5) 
	  ```
- **For ... Else**
  collapsed:: true
	-
	  ```python
	  #case 1
	  for letter in 'foo':
	      print(letter)
	  else:
	      print("All letters have been printed")
	  
	  #case 2
	  for letter in 'foo':
	      print(letter)
	      if letter == 'o':
	          break
	  else:
	      print("Letters have been printed")
	      
	  # Output:
	  # case 1
	  # f
	  # o
	  # o
	  # All letters have been printed
	  # case 2
	  # f
	  # o
	  ```
- **enums with the [[enum]] module**
  collapsed:: true
	-
	  ```python
	  from enum import Enum
	  Season = Enum('Season', 'winter summer spring autumn')
	  print(Season.summer.name)
	  print(Season.summer.value)
	  
	  #using class
	  class Season(Enum):
	      winter = 1
	      summer = 2
	      spring = 3
	      autumn = 4
	  print(Season.winter.name)
	  print(Season.winter.value)
	  
	  # Output:
	  # summer
	  # 2
	  # winter
	  # 1
	  ```
- **Replace len() with enumerate()**
  collapsed:: true
	- Before:
		-
		  ```python
		  # Define a collection, such as list:
		  names = ['Nik', 'Jane', 'Katie', 'Jim', 'Luke']
		  
		  # Using the range(len(collection)) method, you'd write:
		  for i in range(len(names)):
		      print(i, names[i])
		  
		  # Using enumerate, you can define this by writing:
		  for idx, name in enumerate(names):
		      print(idx, name)
		      
		  # Both ways of doing this return:
		  # 0 Nik
		  # 1 Jane
		  # 2 Katie
		  # 3 Jim
		  # 4 Luke
		  ```
	- After:
		-
		  ```python
		  # Define a collection, such as list:
		  names = ['Nik', 'Jane', 'Katie', 'Jim', 'Luke']
		  
		  # Using enumerate, you can define this by writing:
		  for idx, name in enumerate(names, start=1):
		      print(idx, name)
		      
		  # This returns:
		  # 1 Nik
		  # 2 Jane
		  # 3 Katie
		  # 4 Jim
		  # 5 Luke
		  ```
- **Stop Using Square Brackets To Get Dictionary Items — Use .get()**
  collapsed:: true
	- Before:
		-
		  ```python
		  nik = {
		    'age':32,
		    'gender':'male',
		    'employed':True,
		  }
		  
		  print(nik['location'])
		  
		  # Returns:
		  # KeyError: 'location'
		  ```
	- After:
		-
		  ```python
		  nik = {
		    'age':32,
		    'gender':'male',
		    'employed':True,
		  }
		  
		  print(nik.get('location'))
		  
		  # Returns:
		  # None
		  ```
- **Simplify Iterating Over Multiple Lists With Zip()**
  collapsed:: true
	- Before:
		-
		  ```python
		  
		  names = ['Nik', 'Jane', 'Melissa', 'Doug']
		  ages = [32, 28, 37, 53]
		  gender = ['Male', 'Female', 'Female', 'Male']
		  
		  # Old boring way:
		  for_looped = []
		  for i in range(len(names)):
		      for_looped.append((names[i], ages[i], gender[i]))
		  
		  print(for_looped)
		  
		  # Returns:
		  # [('Nik', 32, 'Male'), ('Jane', 28, 'Female'), ('Melissa', 37, 'Female'), ('Doug', 53, 'Male')]
		  ```
	- After:
		-
		  ```python
		  
		  names = ['Nik', 'Jane', 'Melissa', 'Doug']
		  ages = [32, 28, 37, 53]
		  gender = ['Male', 'Female', 'Female', 'Male']
		  
		  # Zipping through lists with zip()
		  zipped = zip(names, ages, gender)
		  zipped_list = list(zipped)
		  
		  print(zipped_list)
		  
		  # Returns:
		  # [('Nik', 32, 'Male'), ('Jane', 28, 'Female'), ('Melissa', 37, 'Female'), ('Doug', 53, 'Male')]
		  ```