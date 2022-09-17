#SQL Zoo Practice:

## SELECT FROM Nobel:

1.
```sql
SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
```

2.
```sql
SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'literature'
```

3.
```sql
SELECT yr, subject FROM nobel WHERE winner = 'Albert Einstein'
```

4.
```sql
SELECT winner FROM nobel WHERE yr >= 2000 AND subject = 'peace'
```

5.
```sql
SELECT yr, subject, winner FROM nobel WHERE yr >= 1980 AND yr <= 1989 AND subject = 'literature'
```

6.
```sql
SELECT * FROM nobel
 WHERE winner IN ('Theodore Roosevelt',
                  'Woodrow Wilson',
                  'Jimmy Carter',
                  'Barack Obama'
                 )
```

7.
```sql
SELECT winner FROM nobel WHERE winner LIKE "John%"
```

8.
```sql
SELECT yr, subject, winner FROM nobel WHERE (yr = 1980 AND subject = 'physics') OR (yr = 1984 AND subject = 'chemistry') 
```

9.
```sql
SELECT yr, subject, winner FROM nobel WHERE yr = 1980 AND subject != 'chemistry' AND subject != 'medicine'
```

10.
```sql
SELECT yr, subject, winner FROM nobel WHERE (subject = 'Medicine' AND yr < 1910) OR (subject = 'Literature' AND yr >= 2004)
```

11.
```sql
SELECT * FROM nobel WHERE winner = 'PETER GRÜNBERG'
```

12.
```sql
SELECT * FROM nobel WHERE winner = 'Eugene O''neill'
```

13.
```sql
SELECT winner, yr, subject FROM nobel WHERE winner LIKE 'Sir%' ORDER BY yr DESC, winner ASC
```

14.
```sql

```