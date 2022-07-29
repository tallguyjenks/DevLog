
## FILTER

### Syntax

```sql
SELECT SUM(<expression>) FILTER (WHERE <condition>)
```

### Example

```sql
SELECT
    physician_last_name,
    COUNT(*) FILTER (WHERE age >= 60) AS “60+”,
    COUNT(*) FILTER (WHERE age >=50 AND age < 60) AS "50s",
    COUNT(*) FILTER (WHERE age >= 40 AND age < 50) AS "40s",
    COUNT(*) FILTER (WHERE age >= 30 AND age < 40) AS "30s",
    COUNT(*) FILTER (WHERE age >= 20 AND age < 30) AS "20s",
    COUNT(*) FILTER (WHERE age >= 13 AND age <20) AS "Teens",
    COUNT(*) FILTER (WHERE age <= 12) AS "12 or younger"
    FROM tutorial.patient_list
GROUP BY 1
ORDER BY 1;
```

![tabular output](/assets/images/2022-03-16-12-43-06.png)
