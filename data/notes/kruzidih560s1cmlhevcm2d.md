

## Deleting A Class Instance

```python
class User
	def __init__(self):
		print("I Live!")
	def say_hi(self):
		print("Hi!")

My_User = User()
#>>> "I Live!"
My_User.say_hi()
#>>> "Hi!"
MY_User
#>>> <__main__.User object at 0x000001BF37B38D30>
del My_User
My_User
#>>> Traceback (most recent call last):
#>>>   File "<stdin>", line 1, in <module>
#>>> NameError: name 'My_User' is not defined
```
