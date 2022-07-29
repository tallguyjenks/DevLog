

## The \_ in Python

- The `_` in python can hold the last value in an interactive shell session but can be used like the unnamed register in [[cli.cmd.vim]] and you can use it to avoid issues when unpacking tuples or just throwing something away:

```python
my_tuple = (1,2,3)
x, _, z = my_tuple # (1,2,3)
#> x = 1
#> _ = 2
#> z = 3
```
