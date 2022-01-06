---
id: TycXAmGbrdITDBnPkkOzt
title: Fstrings
desc: ''
updated: 1641421091010
created: 1641421049730
---

- [Python 3's f-Strings: An Improved String Formatting Syntax (Guide)](https://realpython.com/python-f-strings/)
- F String format specifications

```python
from datetime import datetime
today = datetime.today()
print(f"Today is {today}")
# Today is 2021-07-31 18:20:48.956829
print(f"Today is {today:%B %d, %Y}")
# Today is July 31, 2021
print(f"Today is {today:%m-%d-%Y}")
# Today is 07-31-2021

print(f"Today is {datetime.today()}")
# Today is 2021-07-31 18:20:48.956829

pi = 3.1415926
print(f'Pi is approximately equal to {pi:.2f}')
# Pi is approximately equal to 3.14

id = 1  # need to print a 3-digit number
print(f"The id is {id:03d}")
# The id is 001

N = 1000000000  # need to add separator
print(f'His networth is ${N:,d}')
# His networth is $1,000,000,000
```

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

- to print the repr of the value end the fstring with a `!r`:

```python
x = "hello ✅"
print(f'{x!r}')
# >>> "hello ✅"
```

- to print only ascii values end the fstring with a `!a`:

```python
x = "hello ✅"
print(f'{x!a}')
# >>> "hello \u2705"
```

- to print string values without quotes end the fstring with a `!s`:

```python
x = "hello ✅"
print(f'{x!a}')
# >>> hello ✅
```

---

### Formatting

---

- format fstrings with a colon in the brace and the format on the right hand side

`import datetime; print(f'{datetime.datetime.utcnow():%Y-%m-%d}')`

---

### Nested Formatting

---

```python
num_value = 123.456
nested_format = ".2f"
print(f'{num_value:{nested_format}}')
# >>> 123.46
```
