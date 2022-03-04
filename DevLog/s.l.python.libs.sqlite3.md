---
id: b3n81j0fepx0e13usq5e098
title: Sqlite3
desc: ''
updated: 1641426934533
created: 1641105063868
stub: false
isDir: false
---


- <https://devdocs.io/python~3.9/library/sqlite3>

```python
import sqlite3
conn = sqlite3.connect("example.db")
c = conn.cursor()
c.execute('create table Persons (id int, name text, city text)')
c.execute('insert into Persons VALUES (1, "smith", "dallas")')
conn.commit()
conn.close()
```

```python
import sqlite3
conn = sqlite3.connect('example.db')
c = conn.cursor()
x = c.execute("select * from Persons")
x.fetchall()
[(1, u'smith', u'dallas')]
```
