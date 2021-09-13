- **Loops**
			  collapsed:: true
				- _While Loop_
					-
					  ```python
					  					  					  					  					  					  							  i = 1
					  					  					  					  					  					  							  while i <= 10:
					  					  					  					  					  					  							      print(i)
					  					  					  					  					  					  							      i+=1
					  					  					  					  					  					  							  ```
				- _For Loop_
					-
					  ```python
					  					  					  					  					  					  							  for letter in "giraffe academy":
					  					  					  					  					  					  							      print(letter)
					  					  					  					  					  					  							  
					  					  					  					  					  					  							  friends = ["Jim", "Suzy", "Kevin"]
					  					  					  					  					  					  							  
					  					  					  					  					  					  							  for name in friends:
					  					  					  					  					  					  							      print(name)
					  					  					  					  					  					  							  
					  					  					  					  					  					  							  for index in range(10):
					  					  					  					  					  					  							      print(index) # prints 1-9 not including 10 so always increment upwards by 1
					  					  					  					  					  					  							  ```
			- **Exception Handling**
			  collapsed:: true
				-
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
				  				  				  				  				  ## ./test.py
				  				  				  				  				  ## enter a number: 1
				  				  				  				  				  ## integer division or modulo by zero
				  				  				  				  				  ## Divided By Zero
				  				  				  				  				  ```
			- **Ternary Operator**
			  collapsed:: true
				-
				  ```python
				  #You'll typically see:
				  reputation = 30
				  if reputation > 25:
				      name = "admin"
				  else:
				      name = "visitor"
				  print(name)
				  
				  reputation = 20
				  name = "admin" if reputation > 25 else "visitor"
				  print(name)
				  #>>> admin
				  #>>> visitor
				  ```
			- **Case Statement**
			  collapsed:: true
				- Python 3.10 added Match Case statements
				-
				  ```python
				  x = "hello" 
				  
				  match x:
				  	case "hello":
				      	print("hello")
				    	case "hi":
				     		print("hi")
				    	case _:
				      	print("default case")
				  ```