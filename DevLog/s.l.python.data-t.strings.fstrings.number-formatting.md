---
id: xmln4sas795u1uogj9kc3mf
title: Number Formatting
desc: ''
updated: 1647279755336
created: 1647279748433
---

## Number Formatting

### Floats

```python

pi = 3.1415926
print(f'Pi is approximately equal to {pi:.2f}')
# Pi is approximately equal to 3.14
```

### Integer

```python
id = 1  # need to print a 3-digit number
print(f"The id is {id:03d}")
# The id is 001
```

### Number separator

```python
N = 1000000000  # need to add separator
print(f'His networth is ${N:,d}')
# His networth is $1,000,000,000
```
