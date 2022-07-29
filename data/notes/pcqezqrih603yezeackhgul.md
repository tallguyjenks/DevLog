

> The COPY statement retrieves data from your database and dumps it in the file format of your choosing. For example, take the following statement:

## Data To STDOUT

```sql
COPY (SELECT * FROM customers LIMIT 5) TO STDOUT WITH CSV HEADER;
```

- `COPY` is simply the command used to transfer data to a file format.
- `(SELECT * FROM customers LIMIT 5)` is the query that we want to copy.
- `TO STDOUT` indicates that the results should be printed rather than saved to a file on the hard drive. "Standard Out" is the common term for displaying output in a command-line terminal environment.
- `WITH` is an optional keyword used to separate the parameters that we will use in the database-to-file transfer.
- `CSV` indicates that we will use the CSV file format. We could have also specified `BINARY` or left this out altogether and received the output in text format.
- `HEADER` indicates that we want the header printed as well.

## Data to a file

```sql
COPY (SELECT * FROM customers LIMIT 5) TO '/path/to/my_file.csv' WITH CSV HEADER;
```

## Use psql CLI to get data into the database

```bash
psql -h my_host -p 5432 -d my_database -U my_username
\copy (SELECT * FROM customers LIMIT 5) TO 'my_file.csv' WITH CSV HEADER:
```

- `\copy` is invoking the Postgres `COPY` ... `TO STDOUT`... command to output the data.
- `(SELECT * FROM customers LIMIT 5)` is the query that we want to copy.
- `TO 'my_file.csv'` indicates that psql should save the output from standard into my_file.csv.
- The `WITH CSV HEADER` parameters operate the same as before.

### Configuring the copy command

- `DELIMITER` 'delimiter_character' can be used to specify the delimiter character
for CSV or text files (for example for CSV files, or '`|`' for pipe-separated files)

### Loading data into a table

```bash
\copy customers FROM 'my_file.csv' CSV HEADER DELIMITER
```


