
```sql
BEGIN TRY
--Process that may create an error
END TRY
BEGIN CATCH
--Process to handle error
END CATCH
```

| Function Name     | Function Definition                                                   |
|-------------------|-----------------------------------------------------------------------|
| `ERROR_LINE`      | The line number the error occurred on.                                |
| `ERROR_MESSAGE`   | Plain language description of the error.                              |
| `ERROR_NUMBER`    | The number of the error.                                              |
| `ERROR_PROCEDURE` | The name of the function or stored procedure that produced the error. |
| `ERROR_SEVERITY`  | The severity value of the error.                                      |
| `ERROR_STATE`     | The state number of the error.                                        |

```sql
USE demo

BEGIN TRY
Print 1/0
END TRY
BEGIN CATCH
PRINT 'Error '+CAST(ERROR_NUMBER()AS NVARCHAR(6))+' '+ERROR_MESSAGE()
END CATCH
```
