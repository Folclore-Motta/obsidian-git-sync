# CREATE

The command create is responsible to create databases and tables in SQL

To create a database:

`CREATE DATABASE [database_name] IF NOT EXISTS;`

Example:

```CREATE DATABASE School IF NOT EXISTS;```

You have to be careful creating a DATABASE because if it already exists will be overwrite.

To create a table:

The syntax is:
`CREATE TABLE [table_name]`(
[[Types and Constraints]]...
);

Example:
```SQL
CREATE TABLE student (
	student_id INT AUTO_INCREMENT,
    name VARCHAR(20) NOT NULL,
    major VARCHAR(20) DEFAULT 'undecided'
    PRIMARY KEY(student_id)
);
```

A primary key has both NOT NULL and UNIQUE constraints 

To see the the columns that our database has
```SQL
DESCRIBE student;
```


Manipulation DATA inside the tables

```SQL
INSERT INTO students(name, major)
VALUES
('Clark', 'Biology'),
('Alice', 'Magic');

UPDATE student SET major = 'Something' WHERE major = "Something"
/*Never forgets the WHERE statement*/

DELETE FROM students WHERE student_id = 5;
```

-- <, >, <=, >=, =, <>, AND, OR

IN

