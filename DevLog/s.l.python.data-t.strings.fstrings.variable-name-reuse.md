---
id: rusgrh9bv931axv8nf93qjx
title: Variable Name Reuse
desc: ''
updated: 1647279555222
created: 1647279555222
---

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
