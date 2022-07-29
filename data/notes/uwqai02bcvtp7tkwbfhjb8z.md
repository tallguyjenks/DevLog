

- [[s.l.python]] [TALK / Meredydd Luff / Writing Good Documentation for Developers](https://youtu.be/eWaWvUhpseM?list=PL2Uw4_HvXqvYk1Y5P8kryoyd83L_0Uk5K) #💻️/📖️ #💻️/⭐
- [[s.l.python]] [TALK / Mariatta Wijaya / Oops! I Became an Open Source Maintainer!](https://youtu.be/iPs64t1nsSM?list=PL2Uw4_HvXqvYk1Y5P8kryoyd83L_0Uk5K)
- [[s.l.python]] [[s.l.python.libs.pytest]] [TUTORIAL / Moshe Z / Python Unit Testing with Pytest and Mock](https://youtu.be/DJoffYEPttY?list=PL2Uw4_HvXqvYk1Y5P8kryoyd83L_0Uk5K)
- [[s.l.python]] [Python Features You Probably Don’t Know About, But Should](https://levelup.gitconnected.com/python-features-you-probably-dont-know-about-but-should-a66c6b30c528)

## Named Tuples

```python
from collections import namedtuple

Coordinate = namedtuple("Coordinate", "longitude latitude")
location = Coordinate(90, 37.5)
print("location:", location) 
# accessing attributes with dot notation
print(location.longitude, location.latitude) 
# Output: 
# location: Coordinate(longitude=90, latitude=37.5) 
# (90, 37.5) 
```
## For ... Else

```python
#case 1
for letter in 'foo':
    print(letter)
else:
    print("All letters have been printed")

#case 2
for letter in 'foo':
    print(letter)
    if letter == 'o':
        break
else:
    print("Letters have been printed")
    
# Output:
# case 1
# f
# o
# o
# All letters have been printed
# case 2
# f
# o
```
## enums with the [[s.l.python.libs.enum]] module

```python
from enum import Enum
Season = Enum('Season', 'winter summer spring autumn')
print(Season.summer.name)
print(Season.summer.value)

#using class
class Season(Enum):
    winter = 1
    summer = 2
    spring = 3
    autumn = 4
print(Season.winter.name)
print(Season.winter.value)

# Output:
# summer
# 2
# winter
# 1
```

- [[s.l.python]] [[s.l.python.libs.black]] [[s.l.python.libs.flake8]] [[s.l.python.libs.isort]] <https://medium.com/staqu-dev-logs/keeping-python-code-clean-with-pre-commit-hooks-black-flake8-and-isort-cac8b01e0ea1>
    [[s.l.python.workflow]]

