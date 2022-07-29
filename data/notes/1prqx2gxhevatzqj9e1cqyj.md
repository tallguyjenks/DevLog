

##### Ternary Tests

- [pure bash bible](https://github.com/dylanaraps/pure-bash-bible)

```bash
# Ternary Tests
## Set the value of var to var2 if var2 is greater than var.
## var: variable to set.
## var2>var: Condition to test.
## ?var2: If the test succeeds.
## :var: If the test fails.
((var=var2>var?var2:var))
```
