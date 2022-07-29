

```sql
RANK ( ) OVER ( [ partition_by_clause ] order_by_clause )
```

From <https://docs.microsoft.com/en-us/sql/t-sql/functions/rank-transact-sql?view=sql-server-ver15> 

**Example:**

```sql
RANK() OVER (PARTITION BY PersonID ORDER BY createdDate DESC) AS 'Rank'
```

Partition records based on `personID` this means for each `personID` each record set will be grouped by that then operated on as groupings.

Order by `createdDate` date means that for each `personID` group starting at 1 each record will be ranked in descending order based on the `createdDate`
