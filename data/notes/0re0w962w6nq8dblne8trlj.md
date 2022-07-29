

## For ... Else

```python
#case 1
for letter in 'foo':
print(letter)
else:
print("All letters have been printed")

#case 2
for letter in 'foo':
print(letter)
if letter == 'o':
break
else:
print("Letters have been printed")

# Output:
# case 1
# f
# o
# o
# All letters have been printed
# case 2
# f
# o
```
