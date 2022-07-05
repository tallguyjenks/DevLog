---
id: 35d65udbt42pc3o4m9f2yf7
title: sp_send_dbmail
desc: ''
updated: 1651684211115
created: 1651596632396
---

## Reference

<https://docs.microsoft.com/en-us/sql/relational-databases/system-stored-procedures/sp-send-dbmail-transact-sql?view=sql-server-ver15>

> "The parameters `@recipients`, `@copy_recipients`, and `@blind_copy_recipients` are semicolon-delimited lists of e-mail addresses. At least one of these parameters must be provided, or `sp_send_dbmail` returns an error."

## Setup

1. in [[s.db.ms-sql-server.tools.ssms]] expand the `Management` folder in the Object Explorer
2. Right click on `Database Mail` > `Configure Database Mail` > `Next`
3. `Manage Database Mail accounts and profiles` in the radio button selection list
4. `Next`
5. `Create a new account` this is the email account that will actually be sending the emails for you
   - Gmail is great here because it can be used as a pass through thought you might need to enable additional access in the settings menu of gmail
   - The outcome of this is that you receive emails from that Gmail account but in an automated fashion
6. New account details
   - Account name and description are just for your reference but use them in tandem with the Display name to use an account for each of your Services
   - Email address is the service account email address
   - Display name is what it looks like the email is actually from
   - reply email is who the replies go to
   - server name for gmail would be `smtp.gmail.com` with port number [[n.port.587]]
   - The [[n.protocol.ssl]] checkbox should be ticked
   - Use basic authentication (radio button)
   - username is the service account email address
   - password is the password for the service account email address
7. `Create a new profile`, this is what will be holding the account(s) that send email
8. Give it a name and description
9. add your email account you made to it
10. finish
11. test `sp_send_dbmail`

## Examples

### Simple Message

```sql
EXEC msdb.dbo.sp_send_dbmail
    @profile_name = 'Adventure Works Administrator',
    @recipients = 'yourfriend@Adventure-Works.com',
    @body = 'The stored procedure finished successfully.',
    @subject = 'Automated Success Message' ;
```

### Email message with the results of a query

```sql
EXEC msdb.dbo.sp_send_dbmail
    @profile_name = 'Adventure Works Administrator',
    @recipients = 'yourfriend@Adventure-Works.com',
    @query = 'SELECT COUNT(1)
              FROM AdventureWorks2012.Production.WorkOrder
              WHERE 1 = 1
              AND DueDate > ''2004-04-30''
              AND  DATEDIFF(dd, ''2004-04-30'', DueDate) < 2' ,
    @subject = 'Work Order Count',
    @attach_query_result_as_file = 1 ;
```

### Sending HTML Email

```sql
DECLARE @tableHTML  NVARCHAR(MAX) ;

SET @tableHTML =
    N'<H1>Work Order Report</H1>' +
    N'<table border="1">' +
    N'<tr><th>Work Order ID</th><th>Product ID</th>' +
    N'<th>Name</th><th>Order Qty</th><th>Due Date</th>' +
    N'<th>Expected Revenue</th></tr>' +
    CAST ( ( SELECT
             td = wo.WorkOrderID, '',
             td = p.ProductID, '',
             td = p.Name, '',
             td = wo.OrderQty, '',
             td = wo.DueDate, '',
             td = (p.ListPrice - p.StandardCost) * wo.OrderQty
             FROM AdventureWorks.Production.WorkOrder AS wo
             JOIN AdventureWorks.Production.Product AS p ON wo.ProductID = p.ProductID
             WHERE 1 = 1
             AND DueDate > '2004-04-30'
             AND DATEDIFF(dd, '2004-04-30', DueDate) < 2
             ORDER BY
             DueDate ASC,
             (p.ListPrice - p.StandardCost) * wo.OrderQty DESC
             FOR XML PATH('tr'), TYPE
    ) AS NVARCHAR(MAX) ) +
    N'</table>' ;

EXEC msdb.dbo.sp_send_dbmail @recipients='yourfriend@Adventure-Works.com',
    @subject = 'Work Order List',
    @body = @tableHTML,
    @body_format = 'HTML' ;
```
