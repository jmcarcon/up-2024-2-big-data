What is SQL
===========

_By Juan Manuel Carrillo_.

Introduction
------------

Structured Query Language, or most commonly known as SQL,
is a powerful programming language designed for managing and manipulating
databases that are related between them. It provides a 
standardized way to interact with databases, allowing users to 
define, query, update, and manage data. SQL is widely used in 
the field of database management and is an essential skill 
for anyone working with data-driven applications.

Sql vs. Other Storage Solutions
-------------------------------

SQL (Structured Query Language) and other storage solutions 
represent different approaches to data storage and management. 
SQL is a language used for managing relational databases, 
which organize data into tables with rows and columns. 
Other storage solutions, on the other hand, may include various 
types of databases, file systems, NoSQL databases, and 
distributed storage systems. 

The choice between SQL and other storage solutions depends on 
various factors such as data structure, scalability requirements,
complexity of queries, and specific use case considerations. SQL
databases are well-suited for scenarios where data has a clear
structure and relationships, while NoSQL databases and other 
storage solutions provide flexibility and scalability for diverse
data storage needs. The optimal choice depends on the specific
requirements and characteristics of the application or system
being developed.

Sql Commands
------------

### The SELECT Statement

The `SELECT` statement is used to retrieve data from one
or more tables in a relational database. It is a fundamental 
and essential part of the SQL language and is primarily used 
for querying data. The basic syntax of the SELECT statement 
is as follows:

```sql
SELECT id, name, email
FROM users
WHERE active=1
```

Here's a breakdown of the main components:

- **SELECT**: Specifies the columns that you want to retrieve 
from the database. You can use * to select all columns.

- **FROM**: Specifies the table or tables from which to retrieve
the data.

- **WHERE**: Filters the rows based on a specified condition.
It is used to retrieve only the rows that satisfy the given
condition.

### The INSERT Statement

 The `INSERT` statement is used to insert new records or rows into a table. It allows 
 you to add data to an existing table by specifying the values 
 for each column. The basic syntax for the INSERT statement is 
 as follows:

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

Here's a breakdown of the main components:

- **INSERT INTO**: Specifies the name of the table where you want 
to insert data.
  -  *column1, column2, ...*: Lists the columns into which you 
want to insert values.
- **VALUES**: Keyword indicating the start of the values being 
inserted. 
  - *value1, value2, ...*: Specifies the actual values to be inserted into the corresponding columns.

### The UPDATE Statement
The `UPDATE` statement in SQL is used to modify existing records in a table.
It allows you to change the values of one or more columns based on a specified condition.
The basic syntax for the UPDATE statement is as follows:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition=1;
```
Here's a breakdown of the main components:

- **UPDATE**: Specifies the name of the table that you want to update.
- **SET**:Lists the columns and their new values that you want to update. 
- **WHERE**: Keyword indicating the start of the condition for updating specific rows.

### The DELETE Statement
The `DELETE` statement in SQL is used to remove records from a 
table based on a specified condition. The basic syntax for the DELETE statement is as follows:

```sql
DELETE FROM table_name
WHERE condition;
```
Here's a breakdown of the main components:

- **DELETE**: Specifies the name of the table from which you want to delete records.
- **WHERE**: Keyword indicating the start of the condition for deleting specific rows.
condition: Specifies the condition that determines which rows will be deleted.
If you omit the WHERE clause, all rows in the table will be deleted
...

Sql Clauses
-----------

### The WHERE Clause

The `WHERE` clause The WHERE clause in SQL is used to filter 
records based on a specified condition in SELECT, UPDATE, or 
DELETE statements.

Example:

```sql
SELECT name FROM users WHERE active=1;
```

### The ORDER BY Clause

The `ORDER BY` clause in SQL is used to sort the result set of a 
SELECT statement based on one or more columns.

Example:
```sql
SELECT column1, column2, ... 
FROM table_name 
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC], ...;
```

### The GROUP BY Clause

The `GROUP BY` clause in SQL is used to group rows that have the 
same values in specified columns into summary rows, like 
"total" or "average".

Example:
```sql
SELECT column1, column2, ...
FROM table_name
GROUP BY column1, column2, ...;
```

### The LIMIT Clause
The `LIMIT` clause in SQL is used to restrict the number
of rows returned by a SELECT statement.

Example:
```sql
SELECT column1, column2, ...
FROM table_name
LIMIT number_of_rows;
```

Other Sql Commands
------------------

### The CREATE TABLE Command

The `CREATE TABLE` command in SQL is used to define and
create a new table in a database. The basic syntax for the CREATE TABLE statement is as follows:


```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
    PRIMARY KEY (one or more columns)
    additional constraints (e.g., UNIQUE, NOT NULL, FOREIGN KEY) may be specified here
);
```
Where:

- **CREATE TABLE**: Keywords indicating the start of the table creation.
  - *table_name*: Specifies the name of the table to be created.

  - *column1, column2, ...*: Specifies the columns of the table along with their data types.

  - *datatype*: Specifies the data type of each column (e.g., INT, VARCHAR, DATE).

  - *PRIMARY KEY*: Constraint specifying the primary key for the table, which uniquely identifies each row.

  - *one or more columns*: Columns that form the primary key.

  - *additional constraints*: Other constraints (e.g., UNIQUE, NOT NULL, FOREIGN KEY) can be specified based on your requirements.


### The ALTER TABLE Command

The `ALTER TABLE` statement in SQL is used to modify an existing
table structure, such as adding or dropping columns, modifying 
data types, or adding constraints. The basic syntax for the ALTER
TABLE statement is as follows:

```sql
ALTER TABLE table_name
    ADD COLUMN new_column_name datatype;
    DROP COLUMN column_name;
    MODIFY COLUMN column_name new_datatype;
    ADD CONSTRAINT constraint_name constraint_type (columns);
        other modifications can be specified here
```
Where:

- **ALTER TABLE**: Keywords indicating the start of the table modification.
- **ADD COLUMN**: Keyword indicating the addition of a new column to the table.
- **DROP COLUMN**: Keyword indicating the removal of an existing column from the table.
- **MODIFY COLUMN**: Keyword indicating the modification of the data type of an existing column.
- **ADD CONSTRAINT**: Keyword indicating the addition of a new constraint to the table.

### The DROP TABLE Command

The `DROP TABLE` statement in SQL is used to remove an existing
table and all of its data from the database.

Example:
```sql
DROP TABLE table_name;
```