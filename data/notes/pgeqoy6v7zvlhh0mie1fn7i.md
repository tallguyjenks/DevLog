

```python
def hello_decorator(func):
	def wrapper(*args, **kwargs):
		result = func(*args, **kwargs)
		return result
return wrapper

@hello_decorator
def add(a, b):
	return a + b 

if __name__ == '__main__':
	output = add(2, 2)
	print(output)
```

![alt](assets/images/Pasted_image_20210916111645.png)

- [Python Decorators in 15 Minutes](https://youtu.be/r7Dtus7N4pI) \| [Calm Code Decorators](https://calmcode.io/decorators/introduction.html) #💻️/⭐ 
- [Decorators 101](https://sureshdsk.dev/python-decorators-101)
- [Decorators 201](https://sureshdsk.dev/python-decorators-201)
  - To get the correct doc strings and indicate that wrapping has occurred on the given function we can use the [[s.l.python.libs.functools]] module with the `wraps` function
- [Decorators with params](https://sureshdsk.dev/python-decorators-with-parameters)
  - Useful with using Classes so the extra param passing boiler plate can be avoided
- [3 Essential Decorators in Python You Need To Know](https://betterprogramming.pub/3-essential-decorators-in-python-you-need-to-know-654650bd5c36)
- Can use logging decorators with [[s.l.python.libs.functools]] to log data changes:

```python
from functools import wraps
import datetime as dt

def log_step(func):
  @wraps(func)
  def wrapper(*args, **kwargs):
	  tic = dt.datetime.now()
	  result = func(*args, **kwargs)
	  time_taken = str(dt.datetime.now() - tic)
	  print(f"just ran step {func.__name__} shape={result.shape} took {time_taken}s")
	  return result
  return wrapper
```
