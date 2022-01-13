---
id: Yy2jdsalltaQZQoxGLnuP
title: Variables
desc: ''
updated: 1641854696558
created: 1641854437940
---

## VS Code Stanard Variables

- <https://code.visualstudio.com/docs/editor/userdefinedsnippets>

## Template Variables

Dendron supports various template variables.

- For inserting the current date and time:
  - CURRENT_YEAR: The current year
  - CURRENT_MONTH: The month as two digits (example '02')
  - CURRENT_DAY: The day of the month as two digits (example '08')
  - CURRENT_HOUR: The current hour in 24-hour clock format
  - CURRENT_MINUTE: The current minute as two digits
  - CURRENT_SECOND: The current second as two digits

### Example

```md
Today is {{ CURRENT_YEAR }}.{{ CURRENT_MONTH }}.{{ CURRENT_DAY }},
```

output:

> Today is 2022.01.04
