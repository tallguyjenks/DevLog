
## Printing Ascii

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
