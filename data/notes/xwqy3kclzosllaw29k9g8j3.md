

> To illustrate a simple usage of the COALESCE function, let's return to the customers table. Let's say the marketing team would like a list of the first names, last names, and phone numbers of all male customers. However, for those customers with no phone number, they would like the table to instead write the value 'NO PHONE'. We can accomplish this request with `COALESCE`:
  
```sql
SELECT first_name
     , last_name
     , COALESCE(phone, 'NO PHONE') AS phone
FROM customers
ORDER BY 1;
```

> When dealing with creating default values and avoiding `NULL`, `COALESCE` will always be helpful.

