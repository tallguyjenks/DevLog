
## Resources

- <https://docs.microsoft.com/en-us/sql/relational-databases/json/json-data-sql-server?view=sql-server-ver15>
- <https://docs.microsoft.com/en-us/sql/relational-databases/json/solve-common-issues-with-json-in-sql-server?view=sql-server-ver15>

There are a few key functions for working with JSON in SQL Server.

- `OPENJSON` — open a JSON string into a query-able object
- `FOR` JSON — format data back into a JSON String
- `ISJSON` — check if a string is a valid JSON format
- `JSON_VALUE` — extract a specific value from a JSON object
- `JSON_QUERY` — extract embedded objects and lists from a JSON object
- `JSON_MODIFY` — update values in a JSON object

![function graphic](/assets/images/2022-03-16-13-14-59.png)

## JSON to VARCHAR

```sql
DECLARE @json NVARCHAR(MAX);
SET @json = N'{JSON:HERE}'
```

## Path Expressions

We write JSON “Path Expressions” to get data out of objects with either the `JSON_VALUE` or `JSON_QUERY` Functions.
The Path Expressions allow for the following patterns.

![json path](/assets/images/2022-03-16-13-16-34.png)

## Querying JSON Objects

![querying](/assets/images/2022-03-16-13-17-49.png)

![querying with some json retained](/assets/images/2022-03-16-13-18-42.png)

## Rename Values on Selection

```sql
JSON_MODIFY(<json object>, <path to select>, <new value>)
```

![json modify](/assets/images/2022-03-16-13-19-45.png)

## Lax vs Strict mode

> JSON queries can also use a lax or strict mode to help control the behavior when data does not exist or when fields are not found.
> Specifying the mode at the beginning of a query string will enforce the mode.

```sql
SELECT * FROM OPENJSON(@json, N'lax $.info');
```

![info](/assets/images/2022-03-16-13-20-44.png)
