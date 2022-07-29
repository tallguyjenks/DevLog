

- [x] [If you're not using Python DATA CLASSES yet, you should 🚀](https://youtu.be/vRVVyl9uaZc)
- <https://youtu.be/CvQ7e6yUtnw>

```python
# Regular classes
class Person:
	name: str
	job: str
	age: int
	
	def __init__(self, name, job, age)
		self.name = name
		self.job = job
		self.age = age
		
person1 = Person("Geralt", "Witcher", 30)
person2 = Person("Yennefer", "Sorceress", 25)
person3 = Person("Yennefer", "Sorceress", 25)

print(id(person2))
print(id(person3))
print(person1)

print(person3 == person2)

# Data Class
from dataclasses import dataclass, field

@dataclass(order=True,frozen=False)
class Person:
    sort_index: int = field(init=False, repr=False)
    name: str
    job: str
    age: int
    strength: int = 100

    def __post_init__(self):
        object.__setattr__(self, 'sort_index', self.strength)

    def __str__(self):
        return f'{self.name}, {self.job} ({self.age})'


person1 = Person("Geralt", "Witcher", 30, 99)
person2 = Person("Yennefer", "Sorceress", 25)
person3 = Person("Yennefer", "Sorceress", 25)

print(person1)
print(id(person2))
print(id(person3))
print(person3 == person2)
print(person1 > person2)
```

```python
@dataclass
class Person:
    name: str
    address: str
    active: bool = True
    email_addresses: list[str] = field(default_factory=list)
    id: str = field (init=False, default_factory=generate_id)
    _search_string: str = field(init=False)
    def __post_init__(self) None:
        self. _search_string = f" {self.name} {self.address}"
```
