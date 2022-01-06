---
id: uo0SEJ0ik9H0kXx5rwCQc
title: Temp Tables
desc: ''
updated: 1641414049311
created: 1641105063938
stub: false
isDir: false
---

Temp Tables are result sets that are stored in memory for the live of the connection session. There are two types:

### Local

- Only available for the session that created them.
- Deleted once the session is terminated.
- Denoted with a `#` prepended to the table name.

### Global

- Available for all sessions and users.
- Not deleted until the last session using them is terminated
- CAN be explicitly deleted
- Denoted with `##` prepended to the table name

## Benefits

- Stored in memory and are FAST
- Helps to modularize your code instead of monolithic queries

## Usage

You CAN simply just create the new table but to use the tables iteratively while testing they need to be explicitly deleted for re-use. The best method for this is the following code:

```sql
IF OBJECT_ID('Tempdb.dbo.#table') IS NOT NULL DROP TABLE #table

SELECT *
INTO #table
FROM other_table
WHERE Age > 55
```
