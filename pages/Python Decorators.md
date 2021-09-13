-
			  collapsed:: true
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
				- ![2021_06_03_image.png](https://cdn.logseq.com/%2F07ac90d5-a8a5-495c-84ae-a5c969228e3823d90a39-636b-484a-a9f0-247ff0a7a0bf2021_06_03_image.png?Expires=4776348240&Signature=aullpNqBIYr0X2A8xmDyEjDbWMqCgT812xTe9ViyKqyKBH64h7itp8Ore5U4XyKQ3pC6HbfhoDClIegiG-VaeWfqKnyXhBVZ1eFADMklEExEy0pV64NNrZ9ptrwfpupGTdg2IQHCtgnJppUa2eHuFlcgDAv99oAQf6e2l8UxXLoByhaWOqguYAICMXBkYtklhFSaCORRbZwrjdT9ZrEMrK6HnRrpnfTOY6rmk840A0UACaAeOjFg17ba-VTdL6wLUMcE9Dt0i73khlU5xjKlUqTE5ejBPk-dK8cDsASOCLMhWgMqiSSpZs6MjMSOtL9b3K1fBWiWP7sqt0hDpoVpcQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
			- [Python Decorators in 15 Minutes](https://youtu.be/r7Dtus7N4pI) | [Calm Code Decorators](https://calmcode.io/decorators/introduction.html) #star
			  done:: 1622747738306
			- [Decorators 101](https://sureshdsk.dev/python-decorators-101)
			  todo:: 1620835767488
			- [Decorators 201](https://sureshdsk.dev/python-decorators-201)
			  done:: 1621632285760
			  todo:: 1622738195818
				- To get the correct doc strings and indicate that wrapping has occurred on the given function we can use the [[functools]] module with the `wraps` function
			- [Decorators with params](https://sureshdsk.dev/python-decorators-with-parameters)
			  todo:: 1620835794488
				- Useful with using Classes so the extra param passing boiler plate can be avoided