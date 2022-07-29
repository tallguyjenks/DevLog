

## Pandas Pipe

---

```python
import pandas as pd

df = pd.read_csv('https://calmcode.io/datasets/bigmac.csv')

def set_dtypes(dataf):
  return (dataf
		  .assign(date=lambda d: pd.to_datetime(d['date']))
		  .sort_values(['currency_code', 'date']))

def remove_outliers(dataf):
  min_row_country=32
  countries = (dataf
			  .groupby('currency_code')
			  .agg(n=('name', 'count'))
			  .loc[lambda d: d['n'] >= min_row_country]
			  .index)
  return (dataf
		  .loc[lambda d: d['currency_code'].isin(countries)])

df.pipe(set_dtypes).pipe(remove_outliers)
```

---
