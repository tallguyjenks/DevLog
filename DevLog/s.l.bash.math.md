---
id: ah5dv0ucjmxl8id93q9rr6k
title: Math
desc: ''
updated: 1641429399188
created: 1641429399188
---


#### Arithmetic Expansion

- `(( [arithmetic expression] ))`
- Evaluates the given expression in an arithmetic context.
- That means, strings are considered names of integer variables, all operators are considered arithmetic operators (such as ++, \\=\\=, >, &lt;=, etc..) ==You should always use this for performing tests on numbers!==
- `$(( [arithmetic expression] ))`
- Expands the result of the given expression in an arithmetic context.
- This syntax is similar to the previous, but expands into the result of the expansion. We use it inside other commands when we want the result of the arithmetic expression to become part of another command.
