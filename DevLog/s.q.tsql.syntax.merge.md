---
id: ph7bmf5hzq5fv640skerge5
title: Merge
desc: ''
updated: 1646690054461
created: 1646687976354
---

The process of using `MERGE` works like this.

1. Identify the table you will load data into.
2. Identify the table that you will use as the source of your data.
3. Identify how records in those two tables are connected.
4. Give instructions on what to do when records do not match.
5. Give instructions on what to do when records do match.

## Example

```sql
USE demo

DROP TABLE IF EXISTS Person
DROP TABLE IF EXISTS PersonStageTable

CREATE TABLE Person(
    PersonID BIGINT NOT NULL,
    FirstName NVARCHAR(50) NULL,
    LastName NVARCHAR(50) NULL,
    SourceSystemKey NVARCHAR(50) NULL,
)

CREATE TABLE PersonStageTable(
    PersonID BIGINT NOT NULL,
    FirstName NVARCHAR(50) NULL,
    LastName NVARCHAR(50) NULL,
    SourceSystemKey NVARCHAR(50) NULL,
)

INSERT INTO Person(PersonID, FirstName, LastName, SourceSystemKey)
SELECT 1, 'Bob', 'Wakefield',1

INSERT INTO PersonStageTable(PersonID, FirstName, LastName, SourceSystemKey)
SELECT 1,'Bob','Johnson',1
    UNION
SELECT 2,'Sally','Ride',2

SELECT * FROM Person
SELECT * FROM PersonStageTable


--*****Merge example beings here.*****

MERGE Person AS target
USING (
    SELECT
        PersonID,
        FirstName,
        LastName,
        SourceSystemKey
    FROM PersonStageTable
) AS source
ON (target.SourceSystemKey = source.SourceSystemKey)

WHEN NOT MATCHED THEN
INSERT (
    PersonID,
    FirstName,
    LastName,
    SourceSystemKey
)
VALUES (
    PersonID,
    FirstName,
    LastName,
    SourceSystemKey
)

WHEN MATCHED THEN
UPDATE
SET
target.PersonID = source.PersonID,
target.FirstName = source.FirstName,
target.LastName = source.LastName,
target.SourceSystemKey = source.SourceSystemKey
;

SELECT * FROM Person

DROP TABLE Person
DROP TABLE PersonStageTable
```
