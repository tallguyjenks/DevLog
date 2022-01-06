---
id: rDudgt80QGUa3PsC3cOqy
title: Rename Objects
desc: ''
updated: 1641451058678
created: 1641451053304
---

```sql
ALTER DATABASE [Test1] MODIFY NAME = [Test2]
--or
sp_renamedb 'Test1' , 'Test2
--or
sp_rename 'Test1', 'Test2', 'DATABASE';
```
