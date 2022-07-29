
## Execute Python Script On SQL Server Agent Job

- <https://stackoverflow.com/questions/54680105/how-to-execute-python-script-as-administrator-in-sql-server-agent-job>

```sql
execute sp_execute_external_script 
@language = N'Python', 
@script = N'
a = 1
b = 2
c = a/b
d = a*b
print(c, d)
'
```

OR

> I was able to solve the problem to my question by adding a credential/proxy account, assigning it to the Run as in the step, and then altering the Command to look like this:
> <br>
> `C:\Windows\System32\cmd.exe /C python "C:\PythonScripts\myPython.py"`
