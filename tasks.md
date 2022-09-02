# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
<!-- SELECT * FROM matches WHERE season = '2017'; -->


```

2) Find all the matches featuring Barcelona.

```sql
<!-- SELECT * FROM matches where hometeam = 'Barcelona' or awayteam = 'Barcelona'; -->


```

3) What are the names of the Scottish divisions included?

```sql
<!-- SELECT * FROM matches WHERE division_code LIKE 'SC%' -->
-- SELECT name from divisions where country = 'Scotland'


```

4) Find the division code for the Bundesliga. Use that code to find out how many matches Freiburg have played in the Bundesliga since the data started being collected.

```sql
<!-- SELECT * FROM matches where division_code = 'D1' AND hometeam = 'Freiburg' or awayteam = 'Freiburg'; -->
-- select * FROM divisions Where name = 'Bundesliga'
-- SELECT COUNT(matches) WHERE division_code = 'D1' AND (hometea, ='Frieberg' or awayteam = 'Freiburg')


```

5) Find the unique names of the teams which include the word "City" in their name (as entered in the database)

```sql
<!-- Copy solution here -->
--SELECT DISTINCT hometeam from matches WHERE hometeam LIKE '%City' OR awayteam LIKE '%City'

```

6) How many different teams have played in matches recorded in a French division?

```sql
<!-- Copy solution here -->
--SELECT COUNT(Distinct hometeam) From MATCHES WHERE division_code = 'f1' or division_code = 'F2'
-- SELECT COUNT(DISTINCT hometeam) FROM matches WHERE division_code IN ('F1',''F2);


```

7) Have Huddersfield played Swansea in the period covered?

```sql
<!-- SELECT *FROM matches WHERE awayteam 'Swansea ' AND hometeam = 'Huddersfeild' -->


```

8) How many draws were there in the Eredivisie between 2010 and 2015?

```sql
<!-- SELECT COUNT(*) FROM matches WHERE division_code = 'N1' AND (ftr = 'D' AND season BETWEEN 2010 AND 2015 ) -->


```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. Where there is a tie the match with more home goals should come first.

```sql
<!-- SELECT * FROM matches WHERE ORDER BY (fthg + ftag) DESC, fthg DESC -->


```

10) In which division and which season were the most goals scored?

```sql
<!-- select distinct name, season, max(fthg + ftag)
--from divisions divisions
--join matches matches on divisions.code = matches.division_code
--group by divisions.name, matches.season
--order by max desc;
--limit 1 -->

-- SELECT division_code, season, SUM(fthg + ftag)
--FROM matches 
--GROUP BY division_code, season
-- ORDER BY sum DESC
-- LIMIT 1
```

### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)