
## Link

<https://www.sqlshack.com/introduction-to-sp_executesql-stored-procedure-with-examples/>

## Syntax

```sql
sp_executesql @stmt ,N'@parametername1_datatype,@parametername2_datatype,@parameternameN_datatype'
,@parametername1='Value1' ,@parametername2='Value2',@parameternameN='ValueN'
```

- `@stmt` parameter is used to specify dynamically generated SQL statement or batch. The data type of this parameter must be Unicode strings, for this reason, we have to add N prefix for the direct text usage or have to use nvarchar or nchar data typed variables.
- `@parameternameN_datatype` defines the parameter’s name and data type that has been used in the dynamically constructed SQL statements.
- With the help of the `@parameternameN=’ValueN’` expression, we can assign a value to the defined parameters which are placed in the SQL statement. In the following sections of the article, we will explore the usage details with examples from easy to difficult.

## Example

```sql
DECLARE  @SqlStatment AS NVARCHAR(1000)
DECLARE  @ColNames AS NVARCHAR(100)

SET @ColNames = N'FirstName , MiddleName , LastName';
SET @SqlStatment = 'SELECT ' + @ColNames + ' FROM Person.Person WHERE Persontype=@PerType'

EXECUTE sp_executesql @SqlStatment , N'@PerType nchar(2)',@PerType='EM'
```

### Getting sp_executesql result with output parameter

> `sp_executesql` provides to return execution result of the dynamically constructed SQL statement or batch. The `OUTPUT` parameter plays a key role to resolve this case. In this example, we will count the row number of the PersonPhone table and then we will set the return value to a variable with the `OUTPUT` parameter. The trick of this usage is to indicate the `@RowNumber` parameter as an `OUTPUT` parameter and then we assigned this internal parameter value to the `@Result` parameter:

```sql
DECLARE  @SqlStatment AS NVARCHAR(1000)
DECLARE  @PhoneIdType AS INT
DECLARE  @Result AS INT

SET @SqlStatment='SELECT @RowNumber= COUNT(PhoneNumber) from Person.PersonPhone WHERE PhoneNumberTypeID=@PhoneType'
SET @PhoneIdType=1
EXEC sp_executesql @SqlStatment , N'@PhoneType INT,@RowNumber INT OUTPUT' , @PhoneType=@PhoneIdType ,@RowNumber=@Result OUTPUT

SELECT @Result AS [TableRowNumber]
```

## sp_executesql vs EXEC statement

Useful but `sp_executesql` has the ability to reuse the cached query plans

```sql
DECLARE  @SqlStatment AS NVARCHAR(1000)
    DECLARE  @ColNames AS NVARCHAR(100)
    DECLARE @Persontype AS NVARCHAR(2)= 'EM'
    SET @ColNames = N'FirstName , MiddleName , LastName';
    SET @SqlStatment = 'SELECT ' + @ColNames + ' FROM Person.Person WHERE Persontype=  ''' + @Persontype + ''''
    EXEC(@SqlStatment)
```
