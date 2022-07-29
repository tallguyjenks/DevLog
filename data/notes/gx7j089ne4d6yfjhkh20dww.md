

## Return Newly Inserted Record

When inserting a new record into a table, if you also want that record immediately
returned to the output viewer after insertion just add the `RETURNING` keyword

### Before

```sql
INSERT INTO products ( col1, col2, col3 ) VALUES ( val1, val2, val3 );
```

### After

```sql
-- This returns all fields of the newly inserted record but you can also make
-- the returned value something like just the new PK ID of the record
INSERT INTO products ( col1, col2, col3 ) VALUES ( val1, val2, val3 ) RETURNING *;
```
