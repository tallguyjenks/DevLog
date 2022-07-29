

### List

```python
# basically an array as you understand them

a = [1, 2, 3, 4, 5]
a.append(17) # adds a new item to the end of the list
a.append(19) # adds a new item to the end of the list
a = [1, 2, 3, 4, 5, 17, 19]

a[-1] # shows the item at the end of the list by wrapping around
# you can only wrap around completely, once, otherwise you will get an error.

a[2:5] # this slices out a smaller list. the starting index number element is included and the ending index number is not included so indexes returned will be 2, 3, 4 but not 5

b = ['a', 'b', 'c']
a + b # = [1, 2, 3, 4, 5, 17, 19, 'a', 'b', 'c']
# adding lists together causes concatenation
```
