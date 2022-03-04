---
id: 6stnq9ibn2imczrc3b8vk0b
title: Whitespace and Line Terminations
desc: ''
updated: 1641425019254
created: 1641105063928
stub: false
isDir: false
---


- Python uses whitespace indentation to denote scope without braces.
- It is bad practice to:
  - Use tabs instead of spaces 😭
  - mix whitespace types (tabs with spaces)
- line termination in python files is denoted with the standard `\n`
  - however early on in python to aid in transitions from [[s.l.clang]] languages there is an optional usage of `;` especially to end a line and have multiple statements on a single line like this:
    - `import datetime; print(f'{datetime.datetime.utcnow():%Y-%m-%d}')`

---

- Related:
  - [[r.(.2021.12.13.the-secret-world-of-newline-characters]]

