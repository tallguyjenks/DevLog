- **Functions**
				-
				  ```python
				  				  				  				  				  				  					  def pow(p):
				  				  				  				  				  				  					      """Calculate the power"""
				  				  				  				  				  				  					      return p*p
				  				  				  				  				  				  					  ```
			- **Map Filter Reduce**
				-
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
				  				  				  				  				  				  					  radii = [2, 5, 7.1, 0.3, 10]
				  				  				  				  				  				  					  # map(<function>, <list, tuple, or other iterable object>)
				  				  				  				  				  				  					  list(map(area, radii))
				  				  				  				  				  				  					  print(list(map(area, radii)))
				  				  				  				  				  				  					  # Celcius to Farenheit with map and lambda
				  				  				  				  				  				  					  temps = [("Berlin",29), ("Cairo", 36), ("Buenos Aires", 19), ("Los Angelas", 26), ("Tokyo", 27), ("New York", 28), ("London", 22), ("Beijing", 32)]
				  				  				  				  				  				  					  
				  				  				  				  				  				  					  c_to_f = lambda data: (data[0], (9/5)*data[1] + 32)
				  				  				  				  				  				  					  
				  				  				  				  				  				  					  print(list(map(c_to_f, temps)))
				  				  				  				  				  				  					  
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
			- **The \_\_main\_\_ Function**
				-
				  ```python
				  				  				  				  				  import time
				  				  				  				  				  
				  				  				  				  				  def useful_function():
				  				  				  				  				    for i in range(5):
				  				  				  				  				      print("I sweat I'm useful: {}".format(i))
				  				  				  				  				      time.sleep(1.0)
				  				  				  				  				  
				  				  				  				  				  # This function call if un commented would make it so if the script was run
				  				  				  				  				  # on the CLI then it would execute the function code. However, if we want to 
				  				  				  				  				  # Re-use the code as a module import and not have it run immediately on import
				  				  				  				  				  # Then you need the following logical construct
				  				  				  				  				  # useful_function()
				  				  				  				  				  
				  				  				  				  				  # This code checks if the entry point to the current session is this file.
				  				  				  				  				  # i.e. did we run this file like a script? or are we importing from another 
				  				  				  				  				  # location that is actually "__main__" and we're a sub process declaring
				  				  				  				  				  # variables, functions, and classes? Anything under this construct is ran and 
				  				  				  				  				  # defined only if the script is executed as a stand alone script and not imported
				  				  				  				  				  if __name__ == "__main__":
				  				  				  				  				    useful_function()
				  				  				  				  				  ```
			- **Working with global scope variables from within functions**
				-
				  ```python
				  				  				  				  				  i = 0
				  				  				  				  				  def increment():
				  				  				  				  				      global i
				  				  				  				  				      i += 1
				  				  				  				  				  ```
			- **Functions Can Be Nested**
				-
				  ```python
				  				  				  				  				  def func1(a, b): 
				  				  				  				  				  def inner_func(x):
				  				  				  				  				        return x*x*x 
				  				  				  				  				  return inner_func(a) + inner_func(b)
				  				  				  				  				  ```
			-