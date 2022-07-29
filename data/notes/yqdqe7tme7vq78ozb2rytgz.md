
> **Atomicity**
> A transaction must be an atomic unit of work; either all of its data modifications are performed, or none of them are performed.
>
> **Consistency**
> When completed, a transaction must leave all data in a consistent state.
> In a relational database, all rules must be applied to the transaction's modifications to maintain all data integrity.
> All internal data structures, such as B-tree indexes or doubly-linked lists, must be correct at the end of the transaction.
>
> **Isolation**
> Modifications made by concurrent transactions must be isolated from the modifications made by any other concurrent transactions.
> A transaction either recognizes data in the state it was in before another concurrent transaction modified it, or it recognizes the data after the second transaction has completed, but it does not recognize an intermediate state.
> This is referred to as serializability because it results in the ability to reload the starting data and replay a series of transactions to end up with the data in the same state it was in after the original transactions were performed.
>
> **Durability**
> After a fully durable transaction has completed, its effects are permanently in place in the system.
> The modifications persist even in the event of a system failure.
> SQL Server 2014 (12.x) and later enable delayed durable transactions.
> Delayed durable transactions commit before the transaction log record is persisted to disk.
> For more information on delayed transaction durability, see the article Transaction Durability.
>
> -- <https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-transaction-locking-and-row-versioning-guide?view=sql-server-ver15>
