
```sql
DECLARE @tableHTML NVARCHAR(MAX) =
    N'<h1>Kells Monthly Invoice</h1>' + 
    N'<table border="1">' + 
        N'<tr>' +
            N'<th>Date</th>' + 
            N'<th>Source_Account</th>' + 
            N'<th>Category</th>' + 
            N'<th>Cashflow_In</th>' +
            N'<th>Comment</th>' + 
        N'</tr>'
SET @tableHTML = @tableHTML + CAST((
    SELECT
    td = FORMAT(GETDATE(), 'yyyy-MM'), '',
    td = Source_Account, '',
    td = Category, '',
    td = CAST(Cashflow_In AS NVARCHAR), '',
    td = Comment, ''
	FROM <table>
    FOR XML PATH('tr'), TYPE 
) AS NVARCHAR(MAX))

DECLARE @total NVARCHAR(10) = CAST((SELECT SUM(Cashflow_In) FROM <table>) AS NVARCHAR)

SET @tableHTML = @tableHTML + '<tr><td colspan="3" style="text-align:right;">TOTAL: </td><td>' + @total + '</td><td></td></tr>'

SET @tableHTML = @tableHTML + '</table>'
```
