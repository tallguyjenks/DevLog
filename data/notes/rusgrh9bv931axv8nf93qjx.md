
## Reuse variable name

- f strings that have a trailing `=` will print a statement like this:

```python
x=7
print(f'{x=}')
# >>> x=7
print(f'{x =}')
# >>> x =7
print(f'{x = }')
# >>> x = 7
```
