

```python
# Instead of holding values in memory:

x = range(1_000_000)

# Use a generator that only spits out values as needed

x = (i for i in range(1_000_000))

#  ================================================ #

# Using functions as a generator

def gen(n):
	for i in range(n):
		yield i

for i in gen(5):
	print(i)
	
# V.S.

x = range(5)

for i in x:
	print(i)
		
```
