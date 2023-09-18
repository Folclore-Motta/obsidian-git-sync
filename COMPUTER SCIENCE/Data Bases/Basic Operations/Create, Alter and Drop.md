# Create

The command create is responsible to create databases and tables in SQL

## Create Database

Syntax to create a database:

```
CREATE DATABASE [database_name] IF NOT EXISTS;
```

Example:

```SQL
CREATE DATABASE School IF NOT EXISTS;
```

You have to be careful creating a DATABASE because if it already exists will be overwrite.

## Creating Tables

```
CREATE TABLE [table_name](
Variable_name Type Constraints...
PRIMARY KEY(variable)
FOREING KEY(variable) REFERENCES table_name(variable)
);
```

Related to [[Types and Constraints]].

Example:

```SQL
CREATE TABLE student (
	student_id INT AUTO_INCREMENT,
    name VARCHAR(20) NOT NULL,
    major VARCHAR(20) DEFAULT 'undecided'
    mensal_bill DECIMAL(5,2)
    PRIMARY KEY(student_id)
    FOREING KEY(mensal_bill) REFERENCES student_loams(mensal_bill);
);
```
# Alter

# TO DO


```SQL
ALTER TABLE transactions
DROP INDEX customer_id;
```

```SQL

DROP TABLE student;

ALTER TABLE student ADD gpa DECIMAL(3, 2);

ALTER TABLE student DROP COLUMN gpa;

ALTER TABLE student RENAME COLUMN birth_day TO birth_date; 

ALTER TABLE transactions
MODIFY amount DECIMAL(3,2);
```

# Drop

We can delete databases and tables using drop

Syntax:

```
DROP DATABASE [database_name];
DROP TABLE [table_name];
```

Example

```SQL
DROP DATABASE Schoo; 
DROP TABLE students;
```


Now that we know how to created our table we need to insert information in for that  [[Insert, Update and Delete]].
