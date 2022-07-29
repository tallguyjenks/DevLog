

## Replace len() with enumerate()

### Before

```python
# Define a collection, such as list:
names = ['Nik', 'Jane', 'Katie', 'Jim', 'Luke']

# Using the range(len(collection)) method, you'd write:
for i in range(len(names)):
print(i, names[i])

# Using enumerate, you can define this by writing:
for idx, name in enumerate(names):
print(idx, name)

# Both ways of doing this return:
# 0 Nik
# 1 Jane
# 2 Katie
# 3 Jim
# 4 Luke
```

### After

```python
# Define a collection, such as list:
names = ['Nik', 'Jane', 'Katie', 'Jim', 'Luke']

# Using enumerate, you can define this by writing:
for idx, name in enumerate(names, start=1):
print(idx, name)

# This returns:
# 1 Nik
# 2 Jane
# 3 Katie
# 4 Jim
# 5 Luke
```
