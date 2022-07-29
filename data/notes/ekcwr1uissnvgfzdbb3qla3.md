

## Simplify Iterating Over Multiple Lists With Zip()

### Before

```python

names = ['Nik', 'Jane', 'Melissa', 'Doug']
ages = [32, 28, 37, 53]
gender = ['Male', 'Female', 'Female', 'Male']

# Old boring way:
for_looped = []
for i in range(len(names)):
for_looped.append((names[i], ages[i], gender[i]))

print(for_looped)

# Returns:
# [('Nik', 32, 'Male'), ('Jane', 28, 'Female'), ('Melissa', 37, 'Female'), ('Doug', 53, 'Male')]
```

### After

```python

names = ['Nik', 'Jane', 'Melissa', 'Doug']
ages = [32, 28, 37, 53]
gender = ['Male', 'Female', 'Female', 'Male']

# Zipping through lists with zip()
zipped = zip(names, ages, gender)
zipped_list = list(zipped)

print(zipped_list)

# Returns:
# [('Nik', 32, 'Male'), ('Jane', 28, 'Female'), ('Melissa', 37, 'Female'), ('Doug', 53, 'Male')]
```
