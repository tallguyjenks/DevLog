

- `Link:` <https://python.plainenglish.io/level-up-your-python-code-with-abstract-classes-7f7f6bdcbb5c>
- `Publish Date:` 2021-10-17
- `Reviewed Date:` [[log.daily.2021.11.10]]

---

> you should use abstract classes to specify which methods must be implemented by the child classes. The abc module "make sure" that you implement all those methods before being able to instantiate the objects.

```python
def animate(animal):
	print(animal.get_sound())
	for leg in animal.legs_number:
		print("Moving leg", leg)
	print("Moved!")
```

```python
from abc import ABC, abstractmethod

class Animal(ABC):
	
	@abstractmethod
	def get_sound(self) -> str:
		pass
	
	@property #  you need to add the @propertydecorator both in the abstract class and in every sub-class.
	@abstractmethod
	def legs_number(self) -> int:
		pass

# >>>a = Animal()
# Traceback (most recent call last):
#   File "c:\abstract_class.py", line 9, in <module>
#     a = Animal()
# TypeError: Can't instantiate abstract class Animal with abstract method get_sound

class Cat(Animal):
	
	def get_sound(self) -> str:
		return "Meow"
	
	@property #  you need to add the @propertydecorator both in the abstract class and in every sub-class.
	def legs_number(self) -> int:
  		return 4

# >>> a = Cat()
# >>> a.get_sound()
# Meow

```

![alt](assets/images/Pasted_image_20211105215356.png)

