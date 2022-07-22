Chinook SQL Database - Original Practice Questions

1a. Find the track name and composer name for tracks that have a length between 100,000 and 150,000 ms. Limit the output to the first 10 results, beginning with the longest song.
```sql
SELECT
  Name AS "Track Name"
  ,Composer AS "Composer Name"
	,Milliseconds AS "Length (ms)"
FROM Track
WHERE Milliseconds
	BETWEEN 100000 AND 150000
ORDER BY Milliseconds DESC
LIMIT 10;
```

1b. Some of the Composer names are "NULL"! Instead of Composer, list the artist names of the identified tracks. Find the track name and artist name for tracks that have a length between 100,000 and 150,000 ms. Limit the output to the first 10 results, starting with the longest. HINT: Nested INNER JOIN
```sql
SELECT
	t.name AS "Track Name"
	,a.name AS "Artist Name"
	,t.milliseconds AS "Length (ms)"
FROM Track t
	INNER JOIN Artist a
		ON b.albumid = t.albumId
	INNER JOIN Album b
		ON b.artistid = a.artistid
WHERE t.Milliseconds
	BETWEEN 100000 AND 150000
ORDER BY t.Milliseconds DESC
LIMIT 10;
```
