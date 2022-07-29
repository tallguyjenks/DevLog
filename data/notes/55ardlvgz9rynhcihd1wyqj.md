

<https://medium.com/cognite/postgres-can-do-that-f221a8046e>

- `Author:` alex brasetvik
- `Link:` <https://medium.com/cognite/postgres-can-do-that-f221a8046e>
- `Publish Date:` 2021.12.06
- `Reviewed Date:` [[log.daily.2022.01.26]]

---

- [[s.q.postgres.tips-tricks.query-tuning-with-explain]]
- [[s.q.postgres.tips-tricks.writeable-cte]]

Generate a mandelbrot set

```sql
--Mandelbrot set
WITH RECURSIVE x(i) AS (
	VALUES(0)
	UNION ALL
	SELECT i + 1 FROM x WHERE i < 101
),
Z(Ix, Iy, Cx, Cy, X, Y, I) AS (
	SELECT Ix, Iy, X::float, Y::float, X::float, Y::float, 0
	FROM (SELECT -2.2 + 0.031 * i, i FROM x) AS xgen(x, ix)
		CROSS JOIN (SELECT -1.5 + 0.031 * i, i FROM x) AS ygen(y, iy)
	UNION ALL
		SELECT Ix, Iy, Cx, Cy, X * X - Y * Y + CX AS X, Y * X * 2 + Cy, I + 1
		FROM Z
		WHERE X * X + Y * Y < 16.0 AND I < 27
),
Zt (Ix, Iy, I) AS (
	SELECT Ix, Iy, MAX (I) AS I
	FROM Z
	GROUP BY Iy, Ix
	ORDER BY Iy, Ix
)
SELECT array_to_string(
	array_agg(
		SUBSTRING(
			' .,,,-----++++%%%%@@@@#### ',
			GREATEST (I,1),
			1
		)
	),''
)
FROM Zt
GROUP BY Iy
ORDER BY Iy;
```


