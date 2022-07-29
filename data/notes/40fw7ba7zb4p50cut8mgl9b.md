

```sql
ALTER DATABASE [Test1] MODIFY NAME = [Test2]
--or
sp_renamedb 'Test1' , 'Test2
--or
sp_rename 'Test1', 'Test2', 'DATABASE';
```
