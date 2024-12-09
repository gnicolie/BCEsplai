
# SQL BOLT 
 
 ## SQL Lesson 1: SELECT queries 101

Exercise 1 — Tasks
**Find the title of each film ✓** 

SOL:
`SELECT Title FROM movies;`

**Find the director of each film**

SOL: `SELECT director FROM movies;`

**Find the title and director of each film**

SOL: `SELECT title,director FROM movies;`

**Find the title and year of each film**

SOL:`SELECT title,year FROM movies;`

**Find all the information about each film**

SOL: `SELECT * FROM movies;`

 [Ejercicio 1](https://sqlbolt.com/lesson/select_queries_introduction)

 ## SQL Lesson 2: Queries with constraints (Pt. 1)


Exercise 2 — Tasks
**Find the movie with a row id of 6** 

SOL:
`SELECT * FROM movies WHERE id = 6;` <!-- como lo pongo en diferentes lineas? -->

**Find the movies released in the years between 2000 and 2010 ✓**

SOL: `SELECT * FROM movies WHERE Year >= 2000 AND Year <= 2010;`

**Find the movies not released in the years between 2000 and 2010**

SOL: `SELECT * FROM movies WHERE Year NOT BETWEEN 2000 AND 2010;`

**Find the first 5 Pixar movies and their release year**

SOL:`SELECT * FROM movies WHERE id <= 5;`

 [Ejercicio 2](https://sqlbolt.com/lesson/select_queries_with_constraints)

## SQL Lesson 3: Queries with constraints (Pt. 2)


Exercise 3 — Tasks
**Find all the Toy Story movies** 

SOL:
`SELECT * FROM movies WHERE Title LIKE "Toy Story%";` 

**Find all the movies directed by John Lasseter**

SOL: `SELECT * FROM movies WHERE Director = "John Lasseter";`

**Find all the movies (and director) not directed by John Lasseter**

SOL: `SELECT * FROM movies WHERE Director != "John Lasseter";`

**Find all the WALL-* movies**

SOL:`SELECT * FROM movies WHERE Title LIKE "WALL-_"`

 [Ejercicio 3](https://sqlbolt.com/lesson/select_queries_with_constraints_pt_2)

## SQL Lesson 4: Filtering and sorting Query results


Exercise 4 — Tasks
**List all directors of Pixar movies (alphabetically), without duplicates** 

SOL:
`SELECT DISTINCT Director FROM movies ORDER BY Director ASC;` 

**List the last four Pixar movies released (ordered from most recent to least)**

SOL: `SELECT * FROM movies ORDER BY Year DESC LIMIT 5;`

**List the first five Pixar movies sorted alphabetically**

SOL: `SELECT * FROM movies ORDER BY Title ASC LIMIT 5;`

**List the next five Pixar movies sorted alphabetically**

SOL:`SELECT * FROM movies ORDER BY Title ASC LIMIT 5 OFFSET 5;`

 [Ejercicio 4](https://sqlbolt.com/lesson/filtering_sorting_query_results)



## SQL Review: Simple SELECT Queries


Review 1 — Tasks
**List all the Canadian cities and their populations** 

SOL:
`SELECT * FROM north_american_cities WHERE Country = "Canada";` 

**Order all the cities in the United States by their latitude from north to south**

SOL: `SELECT * FROM north_american_cities WHERE Country = "United States" ORDER BY LATITUDE DESC;`

**List all the cities west of Chicago, ordered from west to east**

SOL: `SELECT * FROM north_american_cities WHERE Longitude < -87.629798 ORDER BY Longitude DESC;`

**List the two largest cities in Mexico (by population)**

SOL:`SELECT * FROM north_american_cities WHERE Country = "Mexico" ORDER BY Population DESC LIMIT 2;`

**List the third and fourth largest cities (by population) in the United States and their population**

SOL:`SELECT city, population FROM north_american_cities WHERE country LIKE "United States" ORDER BY population DESC LIMIT 2 OFFSET 2;`

 [Ejercicio 5](https://sqlbolt.com/lesson/select_queries_review)


## SQL Lesson 6: Multi-table queries with JOINs


Excercise 6 — Tasks
**Find the domestic and international sales for each movie** 

SOL:
`SELECT * FROM movies INNER JOIN Boxoffice ON Id = Movie_id;` 

**Show the sales numbers for each movie that did better internationally rather than domestically**

SOL: `SELECT * FROM movies INNER JOIN Boxoffice ON Id = Movie_id WHERE International_Sales > Domestic_Sales;`

**List all the movies by their ratings in descending order**

SOL: `SELECT * FROM movies INNER JOIN Boxoffice ON Id = Movie_id ORDER BY Rating DESC;`


 [Ejercicio 6](https://sqlbolt.com/lesson/select_queries_with_joins)

## SQL Lesson 7: OUTER JOINs


Excercise 7 — Tasks
**Find the list of all buildings that have employees** 

SOL:
`SELECT DISTINCT building FROM employees;` 

**Find the list of all buildings and their capacity**

SOL: `SELECT * FROM buildings;`

**List all buildings and the distinct employee roles in each building (including empty buildings)**

SOL: `SELECT DISTINCT building_name, role  FROM buildings LEFT JOIN employees ON building_name = building;`


[Ejercicio 7](https://sqlbolt.com/lesson/select_queries_with_outer_joins)

## SQL Lesson 8: A short note on NULLs


Excercise 8 — Tasks

**Find the name and role of all employees who have not been assigned to a building** 

SOL:`SELECT * FROM employees WHERE Building IS NULL;` 

**Find the names of the buildings that hold no employees**

SOL: `SELECT * FROM buildings LEFT JOIN employees ON building_name = building WHERE building IS NULL;`

[Ejercicio 8](https://sqlbolt.com/lesson/select_queries_with_nulls)

## SQL Lesson 9: Queries with expressions


Excercise 9 — Tasks

**List all movies and their combined sales in millions of dollars** 

SOL:

**List all movies and their ratings in percent**

SOL:

**List all movies that were released on even number years**

SOL:

[Ejercicio 8](https://sqlbolt.com/lesson/select_queries_with_nulls)

