- **Data Types**
			  id:: 6100ca2b-21a1-4fbe-babf-ada8c983a200
				- _Strings_
					-
					  ```python
					  					  					  					  					  					  						  # This is an ordinary string
					  					  					  					  					  					  						  print("This is a string")
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # This is a function Doc string
					  					  					  					  					  					  						  def function(x):
					  					  					  					  					  					  						      """This is a doc string explaining
					  					  					  					  					  					  						      the inner workings of this function
					  					  					  					  					  					  						      """
					  					  					  					  					  					  						      y = x * 7
					  					  					  					  					  					  						      reutrn(y)
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  x = 17
					  					  					  					  					  					  						  printer = "hewlet packard"
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # This is a template literal "F string"
					  					  					  					  					  					  						  print(f"I just printed {x} pages to the printer {printer}")
					  					  					  					  					  					  						  # or for less elegence
					  					  					  					  					  					  						  print("I just printed" + x + "pages to the printer" + printer)
					  					  					  					  					  					  						  ```
					- [Python 3's f-Strings: An Improved String Formatting Syntax (Guide)](https://realpython.com/python-f-strings/)
					- F String format specifications
						-
						  ```python
						  from datetime import datetime
						  today = datetime.today()
						  print(f"Today is {today}")
						  # Today is 2021-07-31 18:20:48.956829
						  print(f"Today is {today:%B %d, %Y}")
						  # Today is July 31, 2021
						  print(f"Today is {today:%m-%d-%Y}")
						  # Today is 07-31-2021
						  
						  print(f"Today is {datetime.today()}")
						  # Today is 2021-07-31 18:20:48.956829
						  
						  pi = 3.1415926
						  print(f'Pi is approximately equal to {pi:.2f}')
						  # Pi is approximately equal to 3.14
						  
						  id = 1  # need to print a 3-digit number
						  print(f"The id is {id:03d}")
						  # The id is 001
						  
						  N = 1000000000  # need to add separator
						  print(f'His networth is ${N:,d}')
						  # His networth is $1,000,000,000
						  ```
						-
				- _Nubmers_
					-
					  ```python
					  					  					  					  					  					  						  # Integer whole numbers
					  					  					  					  					  					  						  a = 496
					  					  					  					  					  					  						  print(type(a)) # int for integer
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # Float for floating point number
					  					  					  					  					  					  						  a = 496
					  					  					  					  					  					  						  print(type(a)) # float
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # Complex Numbers (in math i is used for imaginary numbers, in programming and python it is 'j')
					  					  					  					  					  					  						  a = 496 - 6.1j #the j is the complex part
					  					  					  					  					  					  						  print(type(a)) # complex
					  					  					  					  					  					  						  print(a.real) # view the real part of the number
					  					  					  					  					  					  						  print(a.imag) # view the imaginary part of the number
					  					  					  					  					  					  						  ```
				- _Booleans_
					-
					  ```python
					  					  					  					  					  					  						  True & False # these ARE the operators
					  					  					  					  					  					  						  true & false # These are NOT the operators
					  					  					  					  					  					  						  TRUE & FALSE # These are NOT the operators
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  bool(" ") # True
					  					  					  					  					  					  						  bool("")  # False
					  					  					  					  					  					  						  bool(1)   # True
					  					  					  					  					  					  						  bool(0)   # False
					  					  					  					  					  					  						  ```
			- **Data Strcutures**
				- _Set_
					-
					  ```python
					  					  					  					  					  					  						  # a set is like a hashtable, the order is not important and they are not ordered like an array
					  					  					  					  					  					  						  # sets cannot contain duplicate values
					  					  					  					  					  					  						  a = set([1,2,3,4])
					  					  					  					  					  					  						  a = (1, 2, 3, 4)
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # methods
					  					  					  					  					  					  						  a.add() # adds an item to the set
					  					  					  					  					  					  						  a.remove() # removes an existing item from the set
					  					  					  					  					  					  						  a.discard() # acts like remove but if item is not a part of the set, do nothing and throw no errors (remove quietly)
					  					  					  					  					  					  						  a.clear() # removes all items from the set and it becomes empty
					  					  					  					  					  					  						  len(a) # lets you see how many items are in the set
					  					  					  					  					  					  						  # faster way of making a set is to pass an `[]` array to the set() function
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  a = set([1,3,5,7,9])
					  					  					  					  					  					  						  b = set([2,4,6,8,10])
					  					  					  					  					  					  						  c = set([2, 3, 5 ,7])
					  					  					  					  					  					  						  a.union(b) # = 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
					  					  					  					  					  					  						  a.intersection(c) # = 3, 5, 7
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  2 in b # result is True
					  					  					  					  					  					  						  9 not in a # Result is False 9 IS in the set of odd numbers
					  					  					  					  					  					  						  ```
					- _Frozen Set_
						-
						  ```python
						  						  						  						  						  						  							  # less methods than sets
						  						  						  						  						  						  							  # immutable
						  						  						  						  						  						  							  ```
				- _Tuple_
					-
					  ```python
					  					  					  					  					  					  						  # can be created just by assigning values encapsulated in parens
					  					  					  					  					  					  						  # or for a single value leaving a trailing comma
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  a = (1, 2, 3, 4)
					  					  					  					  					  					  						  # or
					  					  					  					  					  					  						  b = ('a',)
					  					  					  					  					  					  						  # or
					  					  					  					  					  					  						  c = 1, 2, 3, 4,
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # tuples are immutable, they are smaller in memory than lists, have less methods available to them, and are faster that lists.
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  survey = (27, "vietnam", True)
					  					  					  					  					  					  						  age, country, knows_python = survey # this works
					  					  					  					  					  					  						  print(age)
					  					  					  					  					  					  						  print(country)
					  					  					  					  					  					  						  print(knows_python)
					  					  					  					  					  					  						  ```
				- _Dictionary_
					-
					  ```python
					  					  					  					  					  					  						  # key value pairs, basically an object in javascript
					  					  					  					  					  					  						  my_dictionary = {"key":"my_key", "value":666}
					  					  					  					  					  					  						  my_dictionary.keys()
					  					  					  					  					  					  						  my_dictionary.values()
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  # to add more key value pairs after initialization to the dictionary use object name and brackets around the key and set equal to the value:
					  					  					  					  					  					  						  my_dictionary["name"] = "Bryan Jenks"
					  					  					  					  					  					  						  # with bracket method the key needs quotes around it but in the constructor function you DONT need quotes on the key names:
					  					  					  					  					  					  						  dict(message="test", language="english")
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  for key, value in my_dictionary.items():
					  					  					  					  					  					  						  	print(key, "=", value)
					  					  					  					  					  					  						  ```
				- _List_
					-
					  ```python
					  					  					  					  					  					  						  # basically an array as you understand them
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  a = [1, 2, 3, 4, 5]
					  					  					  					  					  					  						  a.append(17) # adds a new item to the end of the list
					  					  					  					  					  					  						  a.append(19) # adds a new item to the end of the list
					  					  					  					  					  					  						  a = [1, 2, 3, 4, 5, 17, 19]
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  a[-1] # shows the item at the end of the list by wrapping around
					  					  					  					  					  					  						  # you can only wrap around completely, once, otherwise you will get an error.
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  a[2:5] # this slices out a smaller list. the starting index number element is included and the ending index number is not included so indexes returned will be 2, 3, 4 but not 5
					  					  					  					  					  					  						  
					  					  					  					  					  					  						  b = ['a', 'b', 'c']
					  					  					  					  					  					  						  a + b # = [1, 2, 3, 4, 5, 17, 19, 'a', 'b', 'c']
					  					  					  					  					  					  						  # adding lists together causes concatenation
					  					  					  					  					  					  						  ```