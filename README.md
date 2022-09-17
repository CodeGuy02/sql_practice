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
SELECT winner, subject FROM nobel WHERE yr=1984
ORDER BY
  CASE WHEN subject IN ('Chemistry', 'Physics') THEN 1 ELSE 0 END, subject, winner
```
## SELECT within SELECT

1.
```sql
SELECT name FROM world
  WHERE population >
     (SELECT population FROM world
      WHERE name='Russia')
```

2.
```sql
SELECT name FROM world WHERE gdp/population > (SELECT gdp/population FROM world WHERE name = 'United Kingdom') AND continent = 'europe'
```

3.
```sql
SELECT name, continent FROM world WHERE continent IN (SELECT continent FROM world WHERE name IN ('Argentina', 'Australia')) ORDER BY name
```

4.
```sql
SELECT name, population FROM world WHERE population > (SELECT population FROM world WHERE name = 'United Kingdom') AND population < (SELECT population FROM world WHERE name = 'Germany')
```

5.
```sql
SELECT name AS Name, CONCAT(ROUND(population/(SELECT population FROM world WHERE name = 'Germany')*100,0), '%') AS Percentage FROM world WHERE continent = 'Europe' AND name != 'Germany'
```

6.
```sql
SELECT name FROM world WHERE gdp > ALL(SELECT gdp FROM world WHERE continent = 'europe' AND gdp > 0)
```

7.
```sql
SELECT continent, name, area FROM world x
  WHERE area >= ALL
    (SELECT area FROM world y
        WHERE y.continent=x.continent
          AND population>0)
```

8.
```sql

```

9.
```sql

```

10.
```sql

```
