- [x] [If you're not using Python DATA CLASSES yet, you should 🚀](https://youtu.be/vRVVyl9uaZc)

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

## Pydantic for Data Class Type Hints

> [Do we still need dataclasses? // PYDANTIC tutorial](https://youtu.be/Vj-iU-8_xLs)
> Source: <https://pydantic-docs.helpmanual.io/>

```python
from datetime import datetime
from typing import List, Optional
from pydantic import BaseModel


class User(BaseModel):
    id: int
    name = 'John Doe'
    signup_ts: Optional[datetime] = None
    friends: List[int] = []


external_data = {
    'id': '123',
    'signup_ts': '2019-06-01 12:22',
    'friends': [1, 2, '3'],
}
user = User(**external_data)
print(user.id)
#> 123
print(repr(user.signup_ts))
#> datetime.datetime(2019, 6, 1, 12, 22)
print(user.friends)
#> [1, 2, 3]
print(user.dict())
"""
{
    'id': 123,
    'signup_ts': datetime.datetime(2019, 6, 1, 12, 22),
    'friends': [1, 2, 3],
    'name': 'John Doe',
}
"""
```