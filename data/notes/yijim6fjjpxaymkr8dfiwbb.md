
## Date and number formatting

```python
import datetime
from datetime import datetime
today = datetime.today()
print(f'{datetime.datetime.utcnow():%Y-%m-%d}')
print(f"Today is {today}")
# Today is 2021-07-31 18:20:48.956829
print(f"Today is {today:%B %d, %Y}")
# Today is July 31, 2021
print(f"Today is {today:%m-%d-%Y}")
# Today is 07-31-2021

print(f"Today is {datetime.today()}")
# Today is 2021-07-31 18:20:48.956829
```
