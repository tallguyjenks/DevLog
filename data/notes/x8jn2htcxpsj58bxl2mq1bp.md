

## Ternary Operator

```python
#You'll typically see:
reputation = 30
if reputation > 25:
	name = "admin"
else:
	name = "visitor"
	print(name)

reputation = 20
name = "admin" if reputation > 25 else "visitor"
print(name)
#>>> admin
#>>> visitor
```
