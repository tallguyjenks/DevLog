---
id: auj2du7ghgh5nkd2rfluxxb
title: Select Data into Xml
desc: ''
updated: 1641412749197
created: 1641105063931
stub: false
isDir: false
---


- <https://www.sqlshack.com/working-with-xml-data-in-sql-server/>

```sql
SELECT CAST('<Name><FName>Carol</FName><LName>Elliot</LName></Name>' AS XML)

USE AdventureWorks2012
GO

SELECT Cust.CustomerID,
       OrderHeader.CustomerID,
       OrderHeader.SalesOrderID,
       OrderHeader.Status
FROM Sales.Customer Cust 
	INNER JOIN Sales.SalesOrderHeader OrderHeader
		ON Cust.CustomerID = OrderHeader.CustomerID
FOR XML AUTO;


SELECT * FROM ticketer.sp.ticket 
for xml path ('Ticket'), root('Tickets')
```
