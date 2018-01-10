# Sprint 2: ROI of an Oscar Win

12/7/17

**Author:** Runjini Murthy


__*Project Description:*__ Establish data models, create a SQL database from a set of CSV files, join tables, and query for films that have won an Oscar.


### Summary
This exercise allows you to take CSV files, import them into SQL, use a GUI-interface like SQL Studio to set up data, and ultimately query.  I initially began by researching data sources for Oscar and movie information, with the intent of scraping data.  When that proved beyond the scope of the exercise, I copied and pasted the data in CSV and focused on building data models.  In this case, I built a database constructed of three tables: Movies, pre-Oscar box office results, and post-Oscar box office results.  Within the Movie table, I assigned a Movie_ID primary key.  This information also served as a foreign key in the other two tables, which allows for the join functionality in the query.

Once the three tables were imported using SQL Studio, I reviewed the structure of each table by assigning appropriate data types (i.e. integers for IDs, text for names).  From this point, I researched queries to select, join, and filter data, which ultimately resulted in an output that returned only those movies that had won an Oscar, along with their pre- and post-Oscar weekend box office results.  Further queries/calculations will be needed to determine that monetary affect of an Oscar win.

### SQL Query to Join Tables
```SQL
SELECT Pre_Oscars.Weekend_Gross, Pre_Oscars.Theater_Count, Pre_Oscars.Average, Post_Oscars.Weekend_Gross, Post_Oscars.Theater_Count, Post_Oscars.Average, Movies.Name, Movies."Oscar Winner?"
FROM Pre_Oscars
INNER JOIN Post_Oscars on Post_Oscars.Movie_ID = Pre_Oscars.Movie_ID
INNER JOIN Movies on Movies.ID = Pre_Oscars.Movie_ID
WHERE Movies."Oscar Winner?" = 1

```

### Key SQL Functions
SELECT = choose column from
FROM = table you are taking information from
INNER JOIN = returning values based on matches between tables
WHERE = conditional statement; helpful in filtering

### Helpful Links
[SQLite training] (https://www.quackit.com/sqlite/tutorial/)

[More SQLite training] (http://www.sqlitetutorial.net/)

[SQL Studio training] (https://wiki.sqlitestudio.pl/index.php/)

[And even more SQLite training] (https://www.tutorialspoint.com/sqlite/)

[Inner join vs. outer join] (https://www.diffen.com/difference/Inner_Join_vs_Outer_Join)
