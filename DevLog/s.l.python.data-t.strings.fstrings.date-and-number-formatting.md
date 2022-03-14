---
id: yijim6fjjpxaymkr8dfiwbb
title: Date and Number Formatting
desc: ''
updated: 1647279535497
created: 1647279535497
---

## Date and number formatting

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
