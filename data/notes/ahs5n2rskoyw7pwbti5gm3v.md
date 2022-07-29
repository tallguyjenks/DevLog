

The `LEFT JOIN` is Like the [[T-SQL Inner Join|s.q.tsql.syntax.joins.inner-join]] except instead of throwing out all the single people, if we `LEFT JOIN` Women to Men on `MARRIAGE_ID` then the only records we're throwing out are _all the single ladies_.

The `LEFT JOIN` Keeps every record on the left and adds records that match the condition onto the right side for those matching records. Where there is no match, `NULL` is returned.

_Statements in WHERE or ON clauses may override LEFT JOIN_
