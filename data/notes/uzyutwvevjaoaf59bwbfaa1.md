
## Usage

`SELECT @@ROWCOUNT` in the same execution block to get the result back

```sql
SELECT TOP 1000 * FROM dbo.Customer;
SELECT @@ROWCOUNT;
```

This returns the query results and the count of how many rows from that result set

```sql
SELECT @@ROWCOUNT;
```

executed by itself only returns a count of 1 record (itself).

## Error Handling and Business Rules

> Using SQL Server `@@ROWCOUNT` for Error Handling and Checking a Business Rule

```sql
BEGIN TRAN

UPDATE [Sales].[SalesOrderHeader]
SET [SubTotal] = [SubTotal] * 1.1; -- 10% increase

IF @@ROWCOUNT = 0
    PRINT 'Something went wrong!'
ELSE PRINT 'Rows were updated...'

--COMMIT
ROLLBACK
```

## Instances of Large ROWCOUNT

SQL Server `ROWCOUNT_BIG` function

The data type of `@@ROWCOUNT` is integer. In the cases where a higher number of rows are affected than an integer can handle (meaning more than 2,147,483,647 rows!), you need to use the ROWCOUNT_BIG function. This function returns the data type `bigint`.

```sql
SELECT TOP 1000 * FROM dbo.Customer;
SELECT ROWCOUNT_BIG();
```

## Utilizing ROWCOUNT with Try Catch Statements

```sql
BEGIN TRY
    SELECT TOP 100 * FROM [AdventureWorks2017].[Person].[Person];
END TRY
BEGIN CATCH
    SELECT TOP 50 * FROM [AdventureWorks2017].[Person].[Person];
END CATCH
SELECT @@ROWCOUNT;

/*

@@ROWCOUNT returns zero! This is because the last statement is not the SELECT statement from the TRY block (which has been executed), it’s also not the one from the TRY block as it’s the last SELECT in the script. It’s the TRY/CATCH block itself! @@ROWCOUNT returns the affected rows from any statement, even if it’s not DML or a SELECT query.

To avoid this kind of scenario, you can store the row count in a local variable. The script would then look like this:

*/

DECLARE @rowcount INT;
BEGIN TRY
    SELECT TOP 100 * FROM [AdventureWorks2017].[Person].[Person];
    SET @rowcount = @@ROWCOUNT;
END TRY
BEGIN CATCH
    SELECT TOP 50 * FROM [AdventureWorks2017].[Person].[Person];
    SET @rowcount = @@ROWCOUNT;
END CATCH
SELECT @rowcount;
```
