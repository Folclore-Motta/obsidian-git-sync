
To insert data in the columns you need to specify the table that you want and also the columns, but the columns are opcional because you can insert in the order that the variables are in the table.

Syntax to insert in the table:
```
INSERT INTO [table_name](columns, columns...) VALUES
(first_column, second_column);
```

Example:

```SQL
INSERT INTO students(name, major) VALUES
('Alice', 'Magic');
```

You can also insert multiple values each one in different brackets ():

```SQL
INSERT INTO students(name, major) VALUES
('Clark', 'Biology'),
('Alice', 'Magic');
```

#TODO
Explain that we have orders of insertion because of the relations

UPDATE student SET major = 'Something' WHERE major = "Something"
/*Never forgets the WHERE statement*/

DELETE FROM students WHERE student_id = 5;


-- <, >, <=, >=, =, <>, AND, OR

IN
