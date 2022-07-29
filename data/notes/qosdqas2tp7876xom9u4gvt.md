
> Sometimes you write a complex SQL statement that doesn’t work, and you do not know why. The best way to figure out what is wrong is by ablation testing.
> Ablation testing is where you turn things off until you isolate the problem. In the case of SQL queries, this involves commenting out lines of a complex WHERE clause (or JOIN) until you find the thing that is not working as designed.
> However, if your WHERE clause starts with a filter, you have to move it so you can comment it out. If you start your WHERE clause with 1 = 1, which is always true, then you preserve syntax and can easily comment out your filters without having to rewrite your code.
> No matter how simple your SQL statement is, I recommend that you get in the habit of creating ablation testing ready SQL statements.
>
> -- <https://tutorials.massstreet.net/v/transact-sql/solutions-to-real-world-problems/lesson-50.-setting-up-queries-for-ablation-testing>

```sql
USE AdventureWorks2016

SELECT *
FROM Sales.SalesOrderHeader soh
JOIN Sales.SalesOrderDetail sod ON soh.SalesOrderID = sod.SalesOrderID
WHERE 1 = 1
```

## An Example Of Ablation Testing

Here we suspect that two lines in the WHERE clause are causing our query to act up.

```sql
USE AdventureWorks2016

SELECT
    CONCAT(p.FirstName, ' ',p.LastName) AS SalesPerson,
    DATEPART(month,soh.OrderDate) AS MonthOfSale,
    SUM(sod.LineTotal) AS TotalSales
FROM Person.Person p
    JOIN Sales.SalesPerson sp ON p.BusinessEntityID = sp.BusinessEntityID
    JOIN Sales.SalesOrderHeader soh ON sp.BusinessEntityID = soh.SalesPersonID
    JOIN Sales.SalesOrderDetail sod ON soh.SalesOrderID = sod.SalesOrderDetailID
WHERE 1 = 1
    AND sp.Bonus BETWEEN 3000.00 AND 6000.00
    --AND sp.SalesYTD >= 2000000.00
    --AND sod.UnitPrice < 2000
    AND (YEAR(soh.OrderDate) BETWEEN 2014 AND 2013 OR YEAR(soh.OrderDate) = 2011)
GROUP BY p.LastName, p.FirstName, DATEPART(month,soh.OrderDate)
ORDER BY p.LastName, p.FirstName, DATEPART(month,soh.OrderDate)
```
