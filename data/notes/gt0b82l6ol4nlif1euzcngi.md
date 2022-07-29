

This joins preserves both tables and retains all records but where there are matches it links them up


| Table | One |
| ----- | --- |
| 1     | A   |
| 2     | B   |
| 3     | C   |
| 4     | D   |

| Table | Two  |
| ----- | ---- |
| 1     | C    |
| 2     | D    |
| 3     | NULL |
| 4     | NULL |
| 5     | E    |
| 6     | F    |

| Result | Table One | Table Two |
| ------ | --------- | --------- |
| 1      | A         | C         |
| 2      | B         | D         |
| 3      | C         | NULL      |
| 4      | D         | NULL      |
| 5      | NULL      | E         |
| 6      | NULL      | F         |
