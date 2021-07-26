## Notes
SQL, which stands for Structured Query Language, is a language for interacting with data stored in something called a relational database.
You can think of a relational database as a collection of tables. A table is just a set of rows and columns, like a spreadsheet, which represents exactly one type of entity. For example, a table might represent employees in a company or purchases made, but not both.

Each row, or record, of a table contains information about a single entity. For example, in a table representing employees, each row represents a single person. Each column, or field, of a table contains a single attribute for all rows in the table. 
For example, in a table representing employees, we might have a column containing first and last names for all employees.

## Terminology Alert

1. Super key/ or Key: Attributes(columns/fields) of a relation table that can uniquely identify a record (or a row/tuple).Maximum number of super key a relation table can have are: `(2)^n -1,` where n are number of attributes. This is merely a theoretical concept. We don't use it in databases.
2. Candidate key: 

## Creating the database

```sql
CREATE DATABASE protein;
## This will create a database with the name protein along with various files such as tables, function. So it sort of produces the structure of your database

DROP DATABASE protein;
## Delete database

## Use the database
USE protein;

##This will start using the database and automatically save all the tables to it

CREATE TABLE protein_info (protein_number INT);

## create a table with name protein_info with one column protein number that will hold numeric data.

## Since the protein number can not be NULL you can explicitely define this by:
CREATE TABLE protein_info (protein_number INT NOT NULL);

## Also, if you want this number to increase automatically when new records are added you can use
CREATE TABLE protein_info (protein_number INT NOT NULL AUTO_INCREMENT);

## Since we wish to use protein_number as our primary key so as to uniquely access table records we will specify this explicitly
CREATE TABLE protein_info (
protein_number INT NOT NULL AUTO_INCREMENT,
PRIMARY KEY (protein_number)
);

``` 

###  Introduction to NULL and IS NULL

In SQL,  `NULL`  represents a missing or unknown value. You can check for  `NULL`  values using the expression  `IS NULL`. For example, to count the number of missing birth dates in the  `people`  table:

```
SELECT COUNT(*)
FROM people
WHERE birthdate IS NULL;

```

As you can see,  `IS NULL`  is useful when combined with  `WHERE`  to figure out what data you're missing.

Sometimes, you'll want to filter out missing values so you only get results which are not  `NULL`. To do this, you can use the  `IS NOT NULL`  operator.

For example, this query gives the names of all people whose birth dates are  _not_  missing in the  `people`  table.

```
SELECT name
FROM people
WHERE birthdate IS NOT NULL;
```

## Altering the tables

```sql
## adding new columns protein_name column
ALTER TABLE protein_info
ADD protein_name VARCHAR(255);

## Notes sql doesn't care about line brakes it executes until it encounters ;

## Delete the table
DROP TABLE protein_info;

```

## Entering the data into tables

```sql
INSERT INTO protein_info (protein_name)
VALUES ('Myosin'),('POTED'),('spike');

```
### querying databases
A  _query_  is a request for data from a database table (or combination of tables). Querying is an essential skill for a data scientist, since the data you need for your analyses will often live in databases.

In SQL, you can select data from a table using a  `SELECT`  statement. For example, the following query selects the  `name`  column from the  `people`  table:

```sql
SELECT name
FROM people;

## Change the column name while viewing it
SELECT name AS 'NAME' FROM people;

## This will change the column name from 'name' to capitals 'NAME'.

## To order the table content by contents of name column

SELECT * FROM people ORDER BY name;
```

In this query,  `SELECT`  and  `FROM`  are called keywords. In SQL, keywords are not case-sensitive, which means you can write the same query as:

```sql
select name
from people;
```

That said, it's good practice to make SQL keywords uppercase to distinguish them from other parts of your query, like column and table names.

It's also good practice (but not necessary for the exercises in this course) to include a semicolon at the end of your query. This tells SQL where the end of your query is!


### SELECTing multiple columns

In the real world, you will often want to select multiple columns. Luckily, SQL makes this really easy. To select multiple columns from a table, simply separate the column names with commas!

For example, this query selects two columns,  `name`  and  `birthdate`, from the  `people`  table:

```sql
SELECT name, birthdate
FROM people;
```

Sometimes, you may want to select all columns from a table. Typing out every column name would be a pain, so there's a handy shortcut:

```sql
SELECT *
FROM people;
```

If you only want to return a certain number of results, you can use the  `LIMIT`  keyword to limit the number of rows returned:

```sql
SELECT *
FROM people
LIMIT 10;
```

### WHERE IN

As you've seen,  `WHERE`  is very useful for filtering results. However, if you want to filter based on many conditions,  `WHERE`  can get unwieldy. For example:

```
SELECT name
FROM kids
WHERE age = 2
OR age = 4
OR age = 6
OR age = 8
OR age = 10;
```

Enter the  `IN`  operator! The  `IN`  operator allows you to specify multiple values in a  `WHERE`  clause, making it easier and quicker to specify multiple  `OR`  conditions! Neat, right?

So, the above example would become simply:

```
SELECT name
FROM kids
WHERE age IN (2, 4, 6, 8, 10);
```

### SELECT DISTINCT

Often your results will include many duplicate values. If you want to select all the unique values from a column, you can use the  `DISTINCT`  keyword.

This might be useful if, for example, you're interested in knowing which languages are represented in the  `films`  table:

```sql
SELECT DISTINCT language
FROM films;
```

Remember, you can check out the data in the tables by clicking on the table name!

Before getting started with the instructions below, check out the column names in the  `films`  table!


### Learning to COUNT

What if you want to count the number of employees in your employees table? The  `COUNT`  statement lets you do this by returning the number of rows in one or more columns.

For example, this code gives the number of rows in the  `people`  table:

```sql
SELECT COUNT(*)
FROM people;
```

`COUNT(*)`  tells you how many rows are in a table. However, if you want to count the number of  _non-missing_  values in a particular column, you can call  `COUNT`  on just that column.

For example, to count the number of birth dates present in the  `people`  table:

```sql
SELECT COUNT(birthdate)
FROM people;
```

It's also common to combine  `COUNT`  with  `DISTINCT`  to count the number of  _distinct_  values in a column.

For example, this query counts the number of distinct birth dates contained in the  `people`  table:

```sql
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

```sql
SELECT title
FROM films
WHERE title = 'Metropolis';

```

Notice that the  `WHERE`  clause always comes after the  `FROM`  statement!

**Note that in this course we will use  `<>`  and not  `!=`  for the not equal operator, as per the SQL standard.**

### WHERE AND

Often, you'll want to select data based on multiple conditions. You can build up your  `WHERE`  queries by combining multiple conditions with the  `AND`  keyword.

For example,

```sql
SELECT title
FROM films
WHERE release_year > 1994
AND release_year < 2000;
```

gives you the titles of films released between 1994 and 2000.

Note that you need to specify the column name separately for every  `AND`  condition, so the following would be invalid:

```sql
SELECT title
FROM films
WHERE release_year > 1994 AND < 2000;
```

You can add as many  `AND`  conditions as you need!

### WHERE AND OR

What if you want to select rows based on multiple conditions where some but not  _all_  of the conditions need to be met? For this, SQL has the  `OR`  operator.

For example, the following returns all films released in  _either_  1994 or 2000:

```sql
SELECT title
FROM films
WHERE release_year = 1994
OR release_year = 2000;

```

Note that you need to specify the column for every  `OR`  condition, so the following is invalid:

```sql
SELECT title
FROM films
WHERE release_year = 1994 OR 2000;

```

When combining  `AND`  and  `OR`, be sure to enclose the individual clauses in parentheses, like so:

```sql
SELECT title
FROM films
WHERE (release_year = 1994 OR release_year = 1995)
AND (certification = 'PG' OR certification = 'R');

```

Otherwise, due to SQL's precedence rules, you may not get the results you're expecting!


### BETWEEN

As you've learned, you can use the following query to get titles of all films released in and between 1994 and 2000:

```sql
SELECT title
FROM films
WHERE release_year >= 1994
AND release_year <= 2000;
```

Checking for ranges like this is very common, so in SQL the  `BETWEEN`  keyword provides a useful shorthand for filtering values within a specified range. This query is equivalent to the one above:

```sql
SELECT title
FROM films
WHERE release_year
BETWEEN 1994 AND 2000;
```

It's important to remember that  `BETWEEN`  is  _inclusive_, meaning the beginning and end values are included in the results!


Similar to the  `WHERE`  clause, the  `BETWEEN`  clause can be used with multiple  `AND`  and  `OR`  operators, so you can build up your queries and make them even more powerful!

For example, suppose we have a table called  `kids`. We can get the names of all kids between the ages of 2 and 12 from the United States:

```sql
SELECT name
FROM kids
WHERE age BETWEEN 2 AND 12
AND nationality = 'USA';
```

## Update the table contents

```sql
## update the janes age
UPDATE kids
SET age = 23 WHERE id = 'jane';
```

## Delete the table contents

```sql
DELETE FROM kids WHERE name='jane';

## This will remove entire row for the kid Jane
```

## Other powerful functions
1. Join: Joins two tables based on a foreign key (common colum entries)
If there are two tables i.e. table1 and table2 with common column named table1_id and table2_id then to join them
```sql
SELECT * FROM table1
JOIN table2 ON table1.table1_id = table2.table2_id;

#or 

SELECT * FROM table1
INNER JOIN table2 ON table1.table1_id = table2.table2_id;

## By default the join is inner join
```

LEFT JOIN will include all the records from table1 if specified in code above (since table1 will be present left to LEFT JOIN keyword) and populate corresponding cells with NULL if there are entries missing from table2. RIGHT JOIN is opposite of this.


### LIKE and NOT LIKE

As you've seen, the  `WHERE`  clause can be used to filter text data. However, so far you've only been able to filter by specifying the exact text you're interested in. In the real world, often you'll want to search for a  _pattern_  rather than a specific text string.

In SQL, the  `LIKE`  operator can be used in a  `WHERE`  clause to search for a pattern in a column. To accomplish this, you use something called a  _wildcard_  as a placeholder for some other values. There are two wildcards you can use with  `LIKE`:

The  `%`  wildcard will match zero, one, or many characters in text. For example, the following query matches companies like  `'Data'`,  `'DataC'`  `'DataCamp'`,  `'DataMind'`, and so on:

```
SELECT name
FROM companies
WHERE name LIKE 'Data%';
```

The  `_`  wildcard will match a  _single_  character. For example, the following query matches companies like  `'DataCamp'`,  `'DataComp'`, and so on:

```
SELECT name
FROM companies
WHERE name LIKE 'DataC_mp';
```

You can also use the  `NOT LIKE`  operator to find records that  _don't_  match the pattern you specify.
