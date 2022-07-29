

- `URL:` <https://youtu.be/BxUxX1Ku1EQ>
- `Channel/Host:` mCoding
- `Publish Date:` 2021.06.19
- `Reviewed Date:` [[import.research.video.2021.11.18]]

---

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/BxUxX1Ku1EQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

---

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

**Formatting**

- format fstrings with a colon in the brace and the format on the right hand side

`import datetime; print(f'{datetime.datetime.utcnow():%Y-%m-%d}')`

**Nested Formatting**

```python
num_value = 123.456
nested_format = ".2f"
print(f'{num_value:{nested_format}}')
# >>> 123.46
```

