---
id: jgk0wgxhbjjsohuo1j4b1qy
title: Exception Handling
desc: ''
updated: 1641422448644
created: 1641422448644
---


## Exception Handling

```python
try:
	number = int(input("enter a number: "))
	print(number/0) #divide by zero
except ZeroDivisionError as err:
	print(err)
	print("Divided By Zero")
except ValueError:
	print("invalid input")
# OUTPUT:
## ./test.py
## enter a number: 1
## integer division or modulo by zero
## Divided By Zero
```
