# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
<!-- SELECT * FROM matches WHERE season = 2017; -->


```

2) Find all the matches featuring Barcelona.

```sql
<!-- SELECT * FROM matches WHERE hometeam = 'Barcelona' OR awayteam = 'Barcelona' -->


```

3) What are the names of the Scottish divisions included?

```sql
<!-- SELECT * FROM Divisions WHERE country = 'Scotland'; -->


```

4) Find the division code for the Bundesliga. Use that code to find out how many matches Freiburg have played in the Bundesliga since the data started being collected.

```sql
<!-- SELECT count(division_code) FROM matches WHERE division_code = 'D1' AND hometeam ='Freiburg' OR awayteam = 'Freiburg'; -->


```

5) Find the unique names of the teams which include the word "City" in their name (as entered in the database)

```sql
<!-- SELECT hometeam from matches where hometeam LIKE '%city%'; -->


```

6) How many different teams have played in matches recorded in a French division?

```sql
<!-- SELECT COUNT(DISTINCT hometeam) FROM matches WHERE division_code = 'F1' OR division_code = 'F2'; -->


```

7) Have Huddersfield played Swansea in the period covered?

```sql
<!-- SELECT hometeam,awayteam FROM matches WHERE (hometeam = 'Swansea' AND awayteam = 'Huddersfield') or (awayteam = 'Swansea' AND hometeam = 'Huddersfield'); -->


```

8) How many draws were there in the Eredivisie between 2010 and 2015?

```sql
<!-- SELECT count(division_code) FROM matches WHERE ftr = 'D' AND Season >= 2010 AND season <= 2015; -->


```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. Where there is a tie the match with more home goals should come first.

```sql
<!-- SELECT division_code, hometeam, SUM(fthg) from Matches where division_code = 'E0' GROUP BY division_code, hometeam ORDER BY sum(fthg) DESC; -->


```

10) In which division and which season were the most goals scored?

```sql
<!-- SELECT division_code, season, sum(fthg), sum(ftag) FROM matches GROUP BY division_code, season ORDER BY sum(fthg) DESC; -->


```

### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)