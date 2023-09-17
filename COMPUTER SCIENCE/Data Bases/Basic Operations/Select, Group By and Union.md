# Select

The select command can return us information that we have inserted in the table

Syntax:

```
SELECT columns FROM [table_name];
```

Example:

```SQL
SELECT student_name FROM Students;
```

To get all the rows from a table we use a * which means everything see [[Wildcards]]

```SQL
SELECT * FROM Students;
```

You can also specify the table that you are getting the information from, becomes very helpful with more 

```SQL
SELECT * FROM Students.name, Students.Major;
```

# Order by

You can order the result by another column
- if it's numeric it will be sorted by the number
- if it's text it will be sorted alphabetically

Example:

```SQL
/* Will sort alphabetically */ 
SELECT name, major FROM Students ORDER BY Students.name;
/* Will sort numerically */
SELECT name, major FROM Students ORDER BY Students.id;
```

You can also specify if you want ascending or descending by default ORDER BY is ascending.

```SQL
/* Will alphabetically sort */
SELECT name, major FROM Students ORDER BY name ASC;
/* Will alphabetically inversed sort */
SELECT name, major FROM Students ORDER BY major DESC;
```

# Limit 

You can also specify the amount of outputted data.

```SQL
SELECT * FROM Students LIMIT 10;
```

# Where

It's also possible to specify a condition using WHERE statement to return the exact that that you want.

```SQL
SELECT name, major FROM Students WHERE major="Biology";
SELECT name
```

# Like

And if you want to use [[Wildcards]] in the search you have to use **Like** and **Where**

```SQL
SELECT 
```

# IN, OR, AND

```SQL
SELECT * FROMS Student WHERE major IN ('Biology', 'Chemistry');
```

# Functions

Those are predefined functions in SQL to see the definition of [[Functions]].
## Count

## Distinct

## Avg

## Sum


# Group By

A feature to display data in groups aggregating all rows by a specific column often used with aggregate functions ex: `SUM(), MAX(), MIN(), AVG(), COUNT()`

```SQL
SELECT SUM(amount), order_date
FROM transactions GROUP BY order_date;

  

SELECT MAX(amount), order_date
FROM transactions GROUP BY order_date;

  

SELECT MIN(amount), customer_id

FROM transactions

GROUP BY customer_id;

  

SELECT COUNT(amount), order_date

FROM transactions GROUP BY order_date;

  

SELECT AVG(amount), customer_id

FROM transactions

GROUP BY customer_id

HAVING COUNT(amount) > 1 AND customer_id IS NOT NULL;
```


If you attempt to use WHERE count you'll run into a error instead use the word having you do the same thing