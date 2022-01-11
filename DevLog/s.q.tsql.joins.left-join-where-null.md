---
id: myLukx0Y9Fvw8L5cHvep7
title: Left Join Where Null
desc: ''
updated: 1641413348611
created: 1641105063935
stub: false
isDir: false
---

The same as [[T-SQL Left Join|s.q.tsql.joins.left-join]] except the left side has records removed from is where are are `NULL`'s in the right side.

So this is saying when joining Women to Men on `MARRIAGE_ID` Where `MARRIAGE_ID IS NULL` means you will only see Married Men Returned. No Single Men and no Women at all.