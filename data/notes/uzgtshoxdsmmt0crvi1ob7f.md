

### Set

```python
# a set is like a hashtable, the order is not important and they are not ordered like an array
# sets cannot contain duplicate values
a = set([1,2,3,4])
a = (1, 2, 3, 4)

# methods
a.add() # adds an item to the set
a.remove() # removes an existing item from the set
a.discard() # acts like remove but if item is not a part of the set, do nothing and throw no errors (remove quietly)
a.clear() # removes all items from the set and it becomes empty
len(a) # lets you see how many items are in the set
# faster way of making a set is to pass an `[]` array to the set() function

a = set([1,3,5,7,9])
b = set([2,4,6,8,10])
c = set([2, 3, 5 ,7])
a.union(b) # = 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
a.intersection(c) # = 3, 5, 7

2 in b # result is True
9 not in a # Result is False 9 IS in the set of odd numbers
```
