

related: [[s.l.python.funcs.decorators]]

## Wrapper function

```python
from functools import wraps 

def hello_decorator(func):
"""Simple decorator function""" 
	@wraps(func)
	def wrapper(*args, **kwargs):
		"""Simple decorator wrapper function"""
		result = func(*args, **kwargs)
		return result 

	return wrapper

@hello_decorator
def add(a, b):
	"""Simple function that returns sum of two numbers"""
	return a + b 

@hello_decorator
def multiply(a, b):
	"""Simple function that returns multiplication of two numbers"""
	return a * b 

if __name__ == '__main__': 
	help(add) 

	print(add.__name__)
	print(add.__doc__) 

	output1 = add(2, 2)
	print('Result:: ', output1) 

	print("=" * 25)
	help(multiply)
	print(multiply.__name__)
	print(multiply.__doc__)
	output2 = multiply(4, 2)
	print('Result:: ', output2)
```
