To create a table in SQL

```SQL
CREATE TABLE student (
	student_id INT,
    name VARCHAR(20),
    major VARCHAR(20)
    PRIMARY KEY(student_id)
);
```

To see the the columns that our database has
```SQL
DESCRIBE student;
```

/*
DESCRIBE student;
DROP TABLE student;
ALTER TABLE student ADD gpa DECIMAL(3, 2);
ALTER TABLE student DROP COLUMN gpa;
*/