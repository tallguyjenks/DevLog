
## SQL Server SET NOCOUNT AND SET ROWCOUNT

### SET ROWCOUNT

Although the name, `SET ROWCOUNT` is very similar, it doesn’t impact `@@ROWCOUNT` directly. `SET ROWCOUNT` simply tells SQL Server to stop processing a query after the specified number of rows have been returned, which makes it kind of a “global TOP clause”.

In the following example, we’re limiting the rows to 500. The SELECT query itself should return 1,000 rows, but as you can see `@@ROWCOUNT` tells us only 500 were returned.

![SET ROWCOUNT](/assets/images/2022-03-03-14-02-14.png)

### SET NOCOUNT

`SET NOCOUNT ON` also doesn’t affect `@@ROWCOUNT`. `SET NOCOUNT` tells SQL Server to stop displaying the message with the number of rows affected by a query. However, `@@ROWCOUNT` is still updated.

Let’s illustrate with an example. First the default configuration where `NOCOUNT` is off.

![NOCOUNT](/assets/images/2022-03-03-14-03-56.png)
