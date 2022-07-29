
## pd.ExcelFile

<https://stackoverflow.com/a/17977609/12339658>

```python
xl = pd.ExcelFile('foo.xls')

xl.sheet_names  # see all sheet names

xl.parse(sheet_name)  # read a specific sheet to DataFrame
```

<https://pythoninoffice.com/read-multiple-excel-sheets-with-python-pandas/#:~:text=00%3A00%3A00-,pd.ExcelFile(),-With%20this%20approach>

```python
f = pd.ExcelFile('users.xlsx')
f
# >>> <pandas.io.excel._base.ExcelFile object at 0x00000138DAE66670>
f.sheet_names
# >>> ['User_info', 'purchase', 'compound', 'header_row5']
# To get data from a sheet, we can use the parse() method, and provide the sheet name.
f.parse(sheet_name = 'User_info')
# >>>       User Name Country      City Gender  Age
# >>> 0  Forrest Gump     USA  New York      M   50
# >>> 1     Mary Jane  CANADA   Tornoto      F   30
# >>> 2  Harry Porter      UK    London      M   20
# >>> 3     Jean Grey   CHINA  Shanghai      F   30

```

## pd.read_excel

<https://pythoninoffice.com/read-multiple-excel-sheets-with-python-pandas/>

```python
# Select sheets to read by index: sheet_name = [0,1,2] means the first three sheets.
# Select sheets to read by name: sheet_name = ['User_info', 'compound']. This method requires you to know the sheet names in advance.
# Select all sheets: sheet_name = None.

import pandas as pd
df = pd.read_excel('users.xlsx', sheet_name = [0,1,2])
df = pd.read_excel('users.xlsx', sheet_name = ['User_info','compound'])
df = pd.read_excel('users.xlsx', sheet_name = None) # read all sheets

# We will read all sheets from the sample Excel file, then use that dataframe for the examples going forward.

# The df returns a dictionary of dataframes. The keys of the dictionary contain sheet names, and values of the dictionary contain sheet content.
df.keys()
# >>> dict_keys(['User_info', 'purchase', 'compound', 'header_row5'])

df.values()
# >>> dict_values([      User Name Country      City Gender  Age
# >>> 0  Forrest Gump     USA  New York      M   50
# >>> 1     Mary Jane  CANADA   Tornoto      F   30
# >>> 2  Harry Porter      UK    London      M   20
# >>> 3     Jean Grey   CHINA  Shanghai      F   30,

# >>> ID      Customer            purchase       Date
# >>> 0  101  Forrest Gump        Dragon Ball  2020-08-12
# >>> 1  102     Mary Jane          Evangelion 2020-01-01
# >>> 2  103  Harry Porter        Kill la Kill 2020-08-01
# >>> 3  104     Jean Grey        Dragon Ball  1999-01-01
# >>> 4  105     Mary Jane          Evangelion 2019-12-31
# >>> 5  106  Harry Porter  Ghost in the Shell 2020-01-01
# >>> 6  107     Jean Grey          Evangelion 2018-04-01,
# >>> ])

# To obtain data from a specific sheet, simply reference the key in the dictionary. For example, df['header_row5'] returns the sheet in which data starts from row 5.
df['header_row5']

# >>>    Unnamed: 0    Unnamed: 1          Unnamed: 2           Unnamed: 3
# >>> 0         NaN           NaN                 NaN                  NaN
# >>> 1         NaN           NaN                 NaN                  NaN
# >>> 2         NaN           NaN                 NaN                  NaN
# >>> 3          ID      Customer            purchase                 Date
# >>> 4         101  Forrest Gump        Dragon Ball   2020-08-12 00:00:00
# >>> 5         102     Mary Jane          Evangelion  2020-01-01 00:00:00
# >>> 6         103  Harry Porter        Kill la Kill  2020-08-01 00:00:00
# >>> 7         104     Jean Grey        Dragon Ball   1999-01-01 00:00:00
# >>> 8         105     Mary Jane          Evangelion  2019-12-31 00:00:00
# >>> 9         106  Harry Porter  Ghost in the Shell  2020-01-01 00:00:00
# >>> 10        107     Jean Grey          Evangelion  2018-04-01 00:00:00

```
