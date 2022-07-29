

### Data Structures do not even need to be passed to class \_\_init\_\_ functions

```python
# Data structures like lists and dictionaries dont even need to be passed into the classes init function.
# The data lives at global scope, is mutated by reference not value.


class Mutator:

    def mutate(self):
        data.append(3)  # >>> [0, 1, 2, 3]
        def add_four(data):
            data.append(4)
        add_four(data)  # >>> [0, 1, 2, 3, 4]


if __name__ == "__main__":
    data = [0, 1, 2]
    print(data)  # >>> [0, 1, 2]
    m = Mutator()
    m.mutate()
    print(data)  # >>> [0, 1, 2, 3, 4]

```
