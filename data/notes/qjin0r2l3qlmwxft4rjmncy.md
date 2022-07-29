


```python
from datetime import date
from workalendar.europe import Netherlands

cal = Netherlands(include_carnival=True)
cal.holidays(2021)
```

```python
[(datetime.date(2021, 1, 1), 'New year'),
 (datetime.date(2021, 2, 14), 'Carnival'),
 (datetime.date(2021, 2, 15), 'Carnival'),
 (datetime.date(2021, 2, 16), 'Carnival'),
 (datetime.date(2021, 4, 2), 'Good Friday'),
 (datetime.date(2021, 4, 4), 'Easter Sunday'),
 (datetime.date(2021, 4, 5), 'Easter Monday'),
 (datetime.date(2021, 4, 27), "King's day"),
 (datetime.date(2021, 5, 5), 'Liberation Day'),
 (datetime.date(2021, 5, 13), 'Ascension Thursday'),
 (datetime.date(2021, 5, 23), 'Whit Sunday'),
 (datetime.date(2021, 5, 24), 'Whit Monday'),
 (datetime.date(2021, 12, 25), 'Christmas Day'),
 (datetime.date(2021, 12, 26), 'Boxing Day')]
```

You can also check if a date is a "working date" directly.

```python
cal.is_working_day(date(2020, 12, 23)) # True
cal.is_working_day(date(2020, 12, 25)) # False
```

Another useful function is to check the number of working days between two dates.

```python
cal.get_working_days_delta(date(2018, 4, 2), date(2018, 6, 17))
```

A common use-case for this package will be to use it together with [[pandas|s.l.python.libs.pandas]], so we've added a demo snippet below that shows you the fast way to check if a date is a holiday.

```python
import pandas as pd

# Make a pandas series with holidays of interest
holidates = cal.holidays(2020) + cal.holidays(2021) + cal.holidays(2022)
pd_holidays = pd.to_datetime([d[0] for d in holidates])

# Use vectorised (fast!) .isin method to compare dates
df = pd.DataFrame({"date": pd.date_range(start='2020-01-01', end='2022-01-01')})
df.assign(holiday=lambda d: d['date'].isin(pd_holidays)).loc[lambda d: d['holiday']]
```

---

- Tags: 
  - [[datetime|s.l.python.libs.datetime]]
  - [[time series|time-series]]
- Reference:
  - <https://calmcode.io/shorts/workalendar.py.html>
- Related:
  - [[pandas|s.l.python.libs.pandas]]

