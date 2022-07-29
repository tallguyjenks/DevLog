

### Data Structures are passed by reference not value

```python
# Data structures are passed by reference, not by value.
# So the dictionary can be passed into a class instance, operated upon, and then when the class is over the data itself is mutated
# making it so classes dont need to play hot potato with data. and just just be called and manipulate data at the global state level.

class Mutator:
    def __init__(self, data) -> None:
        self.data = data  # Grab a reference to the data for the class to use internally

    def mutate(self):
        self.data["fname"] = "John"  # Manipulate the data in the class
        print(F"After function call within class instance:\n\t{data}")  # Show result of manipulation


if __name__ == "__main__":
    data = {
        "fname": "Bryan",
        "lname": "Jenks",
        "age": 29,
    }
    print(F"Before function call and at global scope:\n\t{data}")  # show original data in before manipulation
    m = Mutator(data)  # Pass the data into the class
    m.mutate()  # Manipulate the data
    print(F"After class instance, and at global scope:\n\t{data}")  # Show result of manipulation at global scope level (not in class)
```
