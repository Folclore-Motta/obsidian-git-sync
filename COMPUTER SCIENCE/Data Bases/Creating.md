To create a table in SQL

```SQL
CREATE TABLE student (
	student_id INT AUTO_INCREMENT,
    name VARCHAR(20) NOT NULL,
    major VARCHAR(20) DEFAULT 'undecided'
    PRIMARY KEY(student_id)
);
```

A primary key is NOT NULL and UNIQUE

To see the the columns that our database has
```SQL
DESCRIBE student;
```

Manipulation TABLES

```SQL
DESCRIBE student; 

DROP TABLE student;

ALTER TABLE student ADD gpa DECIMAL(3, 2);

ALTER TABLE student DROP COLUMN gpa;

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

