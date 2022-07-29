

|     Data Type     | Range                                                                                                                                                                        | Storage                   |
|:-----------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------|
|   `varchar(x)`    | string of `x` number of bytes "variable character"                                                                                                                           | Variable                  |
|   `nvarchar(x)`   | string of `x` number of bytes "non-variable character"                                                                                                                       | User Defined              |
|     `char(x)`     | string of `x` number of bytes of characters. Unlike `varchar` if you only use 1/50 chars, the other 49 will be taken up with spaces                                          | User Defined              |
|     `bigint`      | -2^63 (-9,223,372,036,854,775,808) to 2^63-1 (9,223,372,036,854,775,807)                                                                                                     | 8 Bytes                   |
|       `int`       | -2^31 (-2,147,483,648) to 2^31-1 (2,147,483,647)                                                                                                                             | 4 Bytes                   |
|    `smallint`     | -2^15 (-32,768) to 2^15-1 (32,767)                                                                                                                                           | 2 Bytes                   |
|     `tinyint`     | 0 to 255                                                                                                                                                                     | 1 Byte                    |
|      `money`      | -922,337,203,685,477.5808 to 922,337,203,685,477.5807 (-922,337,203,685,477.58 to 922,337,203,685,477.58 for Informatica. Informatica only supports two decimals, not four.) | 8 bytes                   |
|   `smallmoney`    | - 214,748.3648 to 214,748.3647                                                                                                                                               | 4 bytes                   |
| `date(s)/time(s)` | [see docs](https://docs.microsoft.com/en-us/sql/t-sql/data-types/date-transact-sql?view=sql-server-ver15)                                                                    |                           |
|      `float`      | - 1.79E+308 to -2.23E-308, 0 and 2.23E-308 to 1.79E+308                                                                                                                      | Depends on the value of n |
|      `real`       | - 3.40E + 38 to -1.18E - 38, 0 and 1.18E - 38 to 3.40E + 38                                                                                                                  | 4 Bytes                   |

---

- Reference:
  - [MS Docs](https://docs.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-ver15)
