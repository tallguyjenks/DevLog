

> Tablib: format-agnostic tabular dataset library



```python
data = tablib.Dataset(headers=['First Name', 'Last Name', 'Age'])
for i in [('Kenneth', 'Reitz', 22), ('Bessie', 'Monke', 21)]:
  data.append(i)


print(data.export('json'))
# [{"Last Name": "Reitz", "First Name": "Kenneth", "Age": 22}, {"Last Name": "Monke", "First Name": "Bessie", "Age": 21}]

print(data.export('yaml'))
# {Age: 22, First Name: Kenneth, Last Name: Reitz}
# {Age: 21, First Name: Bessie, Last Name: Monke}

data.export('xlsx')
# <redacted binary data>

data.export('df')
#   First Name Last Name  Age
# 0    Kenneth     Reitz   22
# 1     Bessie     Monke   21
```
