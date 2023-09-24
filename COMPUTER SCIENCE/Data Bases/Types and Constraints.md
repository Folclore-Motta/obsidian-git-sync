[[Primitive Data Type]]

- Each column of your SQL table is capable of holding data of a particular data type.
- But they are slight different from the the convencional programming data types

# Integers

INT
SMALLINT 
TINYINT 
MEDIUMINT 
BIGINT  
# Floats

DECIMAL 
FLOAT

# Time
DATE
TIME
DATETIME 
TIMESTAMP

# Strings

The difference between CHAR and VARCHAR are that CHAR has fixed size if we defined it as size of 10, and only insert "HI" which has size of 2 the size of the string will continue to be 10, because the 8 left caracteres will be occupied by blank caracteres, different from VARCHAR that will indeed store of caracteres that you asked for not having a fixed size.
 
CHAR 
VARCHAR
TEXT

# Binary
BINARY
BLOB 
BIT

# Others
ENUM
GEOMETRY
LINESTRING

INT = WHOLE NUMBERS
DECIMAL(M, N) = DECIMAL NUMBERS - Exact Value
VARCHAR(1) -- String of text lenght 1
BLOB -- Binary Large Object, Stores Large Data
DATE -- "YYYY--MM-DD"
TIMESTAMP -- "YYYY-MM-DD HH:MM:SS" - used for recording actions

You can also constraints apply properties like
UNIQUE 
NOT NULL 
PRIMARY KEY 
FOREIGN KEY
DEFAULT 'value'
AUTO_INCREMENT 
