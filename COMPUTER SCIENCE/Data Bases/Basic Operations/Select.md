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

To get all the rows from a table we use a * which means everything see [[Regex]]

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

And if you want to use [[Regex]] in the search you have to use **Like** and **Where**

```SQL
SELECT 
```

# IN, OR, AND

```SQL
SELECT * FROMS Student WHERE major IN ('Biology', 'Chemistry');
```

# Functions
## Count

## Distinct

## Avg

## Sum

# Group By

