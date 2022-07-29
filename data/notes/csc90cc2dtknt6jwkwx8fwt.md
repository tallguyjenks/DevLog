
## Link

<https://www.mssqltips.com/sqlservertip/1669/generate-a-parameter-list-for-all-sql-server-stored-procedures-and-functions/>

## Notes

```sql
SELECT 
   SCHEMA_NAME(SO.SCHEMA_ID) AS [Schema],
   SO.Name AS [ObjectName],
   SO.Type_Desc AS [ObjectType (UDF/SP)],
   PM.Parameter_ID AS [ParameterID],
   CASE
      WHEN PM.Parameter_ID = 0 THEN 'Returns'
      ELSE PM.Name
      END AS [ParameterName],
   TYPE_NAME(PM.User_Type_ID) AS [ParameterDataType],
   CASE
      WHEN TYPE_NAME(PM.User_Type_ID) IN ('float', 'uniqueidentifier', 'datetime', 'bit', 'bigint', 'int', 'image', 'money', 'xml', 'varbinary', 'tinyint', 'text', 'ntext', 'smallint', 'smallmoney') THEN ''
      WHEN TYPE_NAME(PM.User_Type_ID) IN ('decimal', 'numeric') THEN '(' + CAST( PM.Precision AS VARCHAR(4) ) + ', ' + CAST( PM.Scale AS VARCHAR(4)) + ')'
      WHEN PM.Max_Length = -1 THEN '(Max)'
      WHEN TYPE_NAME(PM.User_Type_ID) IN ('nvarchar', 'nchar' ) THEN CAST( PM.Max_Length/2 AS VARCHAR(5))
      ELSE CAST( PM.Max_Length AS VARCHAR(5))
      END AS [Size],
   CASE
      WHEN PM.Is_Output = 1 THEN 'Output'
      ELSE 'Input'
      END AS [Direction]
FROM sys.objects AS SO
    INNER JOIN sys.parameters AS PM 
        ON SO.OBJECT_ID = PM.OBJECT_ID
WHERE SO.TYPE IN ('P','FN')
ORDER BY SO.Type_Desc, [Schema], SO.Name, PM.parameter_id;
```
