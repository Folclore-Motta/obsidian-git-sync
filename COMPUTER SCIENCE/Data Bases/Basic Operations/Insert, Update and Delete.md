
# Insert

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

# Update

The command update allow us to change the information that we have previously inserted in the table.

Syntax:

```
UPDATE [table_name] 
SET [variable_name] = "New_value"
WHERE [Conditions];
```

Example:

```SQL
UPDATE student
SET major = "Biology"
WHERE major = "Computer Science" 

```

**Never forget** the WHERE statement otherwise you're going to mess up your entire database because without condition it's gonna change every single row in your table because you didn't specify where to change so it's gonna assume that you want to change everything.

# Delete

We know how to insert how to manipulate and now let's dive into deleting the existing records in a table

Syntax:

```
DELETE FROM [table_name]
WHERE condition
```

Example:

```SQL
DELETE FROM students WHERE student_id = 5;
```

To **Delete, Insert and Update** we presume that you have already created the tables for that you may check [[Create and Drop]].

But know that we have data inside of our tables we might get the information back to us for that check [[Select]].