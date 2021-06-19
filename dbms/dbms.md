## Notes
SQL, which stands for Structured Query Language, is a language for interacting with data stored in something called a relational database.
You can think of a relational database as a collection of tables. A table is just a set of rows and columns, like a spreadsheet, which represents exactly one type of entity. For example, a table might represent employees in a company or purchases made, but not both.

Each row, or record, of a table contains information about a single entity. For example, in a table representing employees, each row represents a single person. Each column, or field, of a table contains a single attribute for all rows in the table. 
For example, in a table representing employees, we might have a column containing first and last names for all employees.

### querying databases
A  _query_  is a request for data from a database table (or combination of tables). Querying is an essential skill for a data scientist, since the data you need for your analyses will often live in databases.

In SQL, you can select data from a table using a  `SELECT`  statement. For example, the following query selects the  `name`  column from the  `people`  table:

```
SELECT name
FROM people;
```

In this query,  `SELECT`  and  `FROM`  are called keywords. In SQL, keywords are not case-sensitive, which means you can write the same query as:

```
select name
from people;
```

That said, it's good practice to make SQL keywords uppercase to distinguish them from other parts of your query, like column and table names.

It's also good practice (but not necessary for the exercises in this course) to include a semicolon at the end of your query. This tells SQL where the end of your query is!


### SELECTing multiple columns

In the real world, you will often want to select multiple columns. Luckily, SQL makes this really easy. To select multiple columns from a table, simply separate the column names with commas!

For example, this query selects two columns,  `name`  and  `birthdate`, from the  `people`  table:

```
SELECT name, birthdate
FROM people;
```

Sometimes, you may want to select all columns from a table. Typing out every column name would be a pain, so there's a handy shortcut:

```
SELECT *
FROM people;
```

If you only want to return a certain number of results, you can use the  `LIMIT`  keyword to limit the number of rows returned:

```
SELECT *
FROM people
LIMIT 10;
```

### SELECT DISTINCT

Often your results will include many duplicate values. If you want to select all the unique values from a column, you can use the  `DISTINCT`  keyword.

This might be useful if, for example, you're interested in knowing which languages are represented in the  `films`  table:

```
SELECT DISTINCT language
FROM films;
```

Remember, you can check out the data in the tables by clicking on the table name!

Before getting started with the instructions below, check out the column names in the  `films`  table!


### Learning to COUNT

What if you want to count the number of employees in your employees table? The  `COUNT`  statement lets you do this by returning the number of rows in one or more columns.

For example, this code gives the number of rows in the  `people`  table:

```
SELECT COUNT(*)
FROM people;
```

`COUNT(*)`  tells you how many rows are in a table. However, if you want to count the number of  _non-missing_  values in a particular column, you can call  `COUNT`  on just that column.

For example, to count the number of birth dates present in the  `people`  table:

```
SELECT COUNT(birthdate)
FROM people;
```

It's also common to combine  `COUNT`  with  `DISTINCT`  to count the number of  _distinct_  values in a column.

For example, this query counts the number of distinct birth dates contained in the  `people`  table:

```
SELECT COUNT(DISTINCT birthdate)
FROM people;
```
### Filtering in SQL
In SQL, the  `WHERE`  keyword allows you to filter based on both text and numeric values in a table. There are a few different comparison operators you can use:

-   `=`  equal
-   `<>`  not equal
-   `<`  less than
-   `>`  greater than
-   `<=`  less than or equal to
-   `>=`  greater than or equal to

For example, you can filter text records such as  `title`. The following code returns all films with the title  `'Metropolis'`:

```
SELECT title
FROM films
WHERE title = 'Metropolis';

```

Notice that the  `WHERE`  clause always comes after the  `FROM`  statement!

**Note that in this course we will use  `<>`  and not  `!=`  for the not equal operator, as per the SQL standard.**

### WHERE AND

Often, you'll want to select data based on multiple conditions. You can build up your  `WHERE`  queries by combining multiple conditions with the  `AND`  keyword.

For example,

```
SELECT title
FROM films
WHERE release_year > 1994
AND release_year < 2000;
```

gives you the titles of films released between 1994 and 2000.

Note that you need to specify the column name separately for every  `AND`  condition, so the following would be invalid:

```
SELECT title
FROM films
WHERE release_year > 1994 AND < 2000;
```

You can add as many  `AND`  conditions as you need!

### WHERE AND OR

What if you want to select rows based on multiple conditions where some but not  _all_  of the conditions need to be met? For this, SQL has the  `OR`  operator.

For example, the following returns all films released in  _either_  1994 or 2000:

```
SELECT title
FROM films
WHERE release_year = 1994
OR release_year = 2000;

```

Note that you need to specify the column for every  `OR`  condition, so the following is invalid:

```
SELECT title
FROM films
WHERE release_year = 1994 OR 2000;

```

When combining  `AND`  and  `OR`, be sure to enclose the individual clauses in parentheses, like so:

```
SELECT title
FROM films
WHERE (release_year = 1994 OR release_year = 1995)
AND (certification = 'PG' OR certification = 'R');

```

Otherwise, due to SQL's precedence rules, you may not get the results you're expecting!


### BETWEEN

As you've learned, you can use the following query to get titles of all films released in and between 1994 and 2000:

```
SELECT title
FROM films
WHERE release_year >= 1994
AND release_year <= 2000;
```

Checking for ranges like this is very common, so in SQL the  `BETWEEN`  keyword provides a useful shorthand for filtering values within a specified range. This query is equivalent to the one above:

```
SELECT title
FROM films
WHERE release_year
BETWEEN 1994 AND 2000;
```

It's important to remember that  `BETWEEN`  is  _inclusive_, meaning the beginning and end values are included in the results!
