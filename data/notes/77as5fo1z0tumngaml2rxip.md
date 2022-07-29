

> “A class should have one, and only one, reason to change”

```python
import numpy as np

def math_operations(list_):
    # Compute Average
    print(f"the mean is {np.mean(list_)}")
    # Compute Max
    print(f"the max is {np.max(list_)}") 

math_operations(list_ = [1,2,3,4,5])
# the mean is 3.0
# the max is 5
```

Having a single function do all the work is a bad approach

split the function `math_operations` into atomic functions

Make a single function (or class), generically named, "main". This will call all the other functions one-by-one in a step-to-step process.

```python
def get_mean(list_):
    '''Compute Mean'''
    print(f"the mean is {np.mean(list_)}") 

def get_max(list_):
    '''Compute Max'''
    print(f"the max is {np.max(list_)}") 

def main(list_): 
    # Compute Average
    get_mean(list_)
    # Compute Max
    get_max(list_)

main([1,2,3,4,5])
# the mean is 3.0
# the max is 5
```

The result of this simple action is that now:

- It is easier to localize errors. Any error in execution will point out to a smaller section of your code, accelerating your debug phase.
- Any part of the code is reusable in other section of your code.
- Moreover and, often overlooked, is that it is easier to create testing for each function of your code. 
  - _Side note on testing:_ You should write tests before you actually write the script. But, this is often ignored in favor of creating some nice result to be shown to the stakeholders instead.

---

- Reference:
  - [[SOLID Coding in Python|r.(.2021.11.10.solid-coding-in-python]]

