

> “Many client-specific interfaces are better than one general-purpose interface”
> <br>
> In the contest of classes, an interface is considered, all the methods and properties “**exposed**”, thus, everything that a user can interact with that belongs to that class.
> <br>
> In this sense, the The Interface Segregation Principle tell us that a class should only have the interface needed ([[the-single-responsibility-principle|r.{.clean-code.the-single-responsibility-principle]]) and avoid methods that won’t work or that have no reason to be part of that class.
> <br>
> This problem arises, primarily, when, a subclass inherits methods from a base class that it does not need.

```python
import numpy as np
from abc import ABC, abstractmethod

class Mammals(ABC):
    @abstractmethod
    def swim() -> bool:
        print("Can Swim") 

    @abstractmethod
    def walk() -> bool:
        print("Can Walk") 

class Human(Mammals):
    def swim():
        return print("Humans can swim") 

    def walk():
        return print("Humans can walk") 

class Whale(Mammals):
    def swim():
        return print("Whales can swim") 
	
# ========================================= #
Human.swim()
Human.walk()

Whale.swim()
Whale.walk()

# Humans can swim
# Humans can walk
# Whales can swim
# Can Walk
```

The sub-class whale can still invoke the method “walk” but it shouldn’t, and we must avoid it.

The way suggested by `ISP` is to create more client-specific interfaces rather than one general-purpose interface. So, our code example becomes:

```python
from abc import ABC, abstractmethod

class Walker(ABC):
  @abstractmethod
  def walk() -> bool:
    return print("Can Walk") 

class Swimmer(ABC):
  @abstractmethod
  def swim() -> bool:
    return print("Can Swim") 

class Human(Walker, Swimmer):
  def walk():
    return print("Humans can walk") 
  def swim():
    return print("Humans can swim") 

class Whale(Swimmer):
  def swim():
    return print("Whales can swim") 

if __name__ == "__main__":
  Human.walk()
  Human.swim()

  Whale.swim()
  Whale.walk()

# Humans can walk
# Humans can swim
# Whales can swim
```

---

- ## Tags:
- Reference:
  - [[SOLID Coding in Python|r.(.2021.11.10.solid-coding-in-python]]
- Related:
  - [[Python Abstract Base Classes|s.l.python.oop.abstract-base-classes]]

