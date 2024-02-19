# Structured Query Language (SQL)

Structured Query Language, or most commonly known as SQL,
is a powerful programming language designed for managing and manipulating
databases that are related between them. It provides a 
standardized way to interact with databases, allowing users to 
define, query, update, and manage data. SQL is widely used in 
the field of database management and is an essential skill 
for anyone working with data-driven applications.

## Key Concepts
Some of the most common concepts used inside SQL are:

### 1. Database
A database is a structured collection of data that is organized 
and stored for easy access and management. SQL allows users to 
create and manage databases efficiently.

### 2. Table
In SQL, data is stored in tables, which are structured 
collections of rows and columns. Each column has a specific data
type, and each row represents a record in the table.

### 3. Query
SQL enables users to retrieve specific data from a database 
using queries. **Queries** are statements that define the criteria 
for selecting and retrieving data from one or more tables.

### 4. CRUD Operations
SQL supports CRUD operations: 
- Create
- Read
- Update
- Delete

Users can insert new data into tables, modify, update or delete 
unwanted data.

### 5. Relationships
SQL allows the establishment of relationships between tables, 
defining how data in a table relates to data in another. 
Some of these relationships include one-to-one, one-to-many, 
and many-to-many.

## Example Query

Here is a simple SQL query, to illustrate all that was said:

```sql
SELECT name, manager
FROM employees
WHERE department = 'Finance';