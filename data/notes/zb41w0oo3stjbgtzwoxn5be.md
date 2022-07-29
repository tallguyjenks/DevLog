

```sql
DATEPART ( datepart , date )
```

| datepart    | Abbreviations |
| ----------- | ------------- |
| year        | yy, yyyy      |
| quarter     | qq, q         |
| month       | mm, m         |
| dayofyear   | dy, y         |
| day         | dd, d         |
| week        | wk, ww        |
| weekday     | dw            |
| hour        | hh            |
| minute      | mi, n         |
| second      | ss, s         |
| millisecond | ms            |
| microsecond | mcs           |
| nanosecond  | ns            |
| tzoffset    | tz            |
| iso_week    | isowk, isoww  |

Returns an INT

```sql
SELECT DATEPART(datepart,'2007-10-30 12:15:32.1234567 +05:10')
```

| datepart               | Return value |
| ---------------------- | ------------ |
| year, yyyy, yy         | 2007         |
| quarter, qq, q         | 4            |
| month, mm, m           | 10           |
| dayofyear, dy, y       | 303          |
| day, dd, d             | 30           |
| week, wk, ww           | 44           |
| weekday, dw            | 3            |
| hour, hh               | 12           |
| minute, n              | 15           |
| second, ss, s          | 32           |
| millisecond, ms        | 123          |
| microsecond, mcs       | 123456       |
| nanosecond, ns         | 123456700    |
| tzoffset, tz           | 310          |
| iso_week, isowk, isoww | 44           |
