# MySql-CheatSheet

## ⛄ Table of Content

* [1. Introduction](#Introduction)
* [2. Database-Table](#Database-Table)
* [3. Inserting-Data](#Inserting-Data)
* [4. Select-And-Where](#Select-And-Where)
* [5. Constraints](#Constraints)

# Introduction

## What is a database?
    
`A database is an organized collection of structured information or data.`

## What is DBMS?

`Database Management Systems (DBMS) are software systems used to store, retrieve, and run queries on data.`

It is of two types:

- `Relational (SQL)`
    
    A relational database is a collection of data items with pre-defined relationships between them, stored in the form of tables, rows, and columns.

    Examples: MySQL, Oracle, PostgreSQL.

- `Non-Relational (No-SQL)`

    NoSQL databases are non-relational, offering flexible schemas, scalability, and support for diverse data models. Commonly used in web development, analytics, and content management for handling large and dynamic data.
    
    Examples: MongoDB, Cassandra, Redis. 

    ![--r](https://github.com/k-sameer701/Learn-MySql/assets/103239208/901affca-cdfb-4dc6-b431-8f197415267b)
    
## What is MySQL?

`MySQL is a relational database management system (RDBMS) developed by Oracle i.e. based on structured query language (SQL).`

# Database-Table
## What is a database table?
`A database table is a collection of rows and columns that contains relational data.`

![table](https://github.com/k-sameer701/Learn-SQL/assets/103239208/4666a64d-aa02-4580-8261-f3ff67fc216a)

### 👻 Create a Database:

#### Syntax:
    CREATE DATABASE database_name;

#### Example: 
    CREATE DATABASE mydatabase;

### 👻 Switch to the Created Database:

#### Syntax: 
    USE database_name;

#### Example: 
    USE mydatabase;

###  👻 Create Tables:
Define table structure with columns and data types.

#### Syntax:
    CREATE TABLE table_name 
    (
        column1 datatype1,
        column2 datatype2,
        ...
    );
    
#### Example:
    CREATE TABLE users
    (
        id int unsigned,
        name varchar(100),
        email varchar(150),
        password varchar(100),
        contact varchar(15),
        address text,
        dob date,
        gender enum("M", "F", "O"),
        status boolean
    );

#### 👻 Categories of DataTypes in SQL:

- Strings
- Numeric
- Date & Time


`💀 String Data Types`

1. **CHAR(n):**
   Fixed-length character string.

2. **VARCHAR(n):**
   Variable-length character string.

3. **TEXT:**
   Variable-length character string with no specified limit.

4. **TINYTEXT:**
    A very small variable-length character string.

5. **MEDIUMTEXT:**
   A medium-sized variable-length character string.

6. **LONGTEXT:**
   A long variable-length character string.

7. **BINARY(n):**
   Fixed-length binary string.

8. **VARBINARY(n):**
   Variable-length binary string.

9. **BLOB:**
   Variable-length binary large object.

10. **TINYBLOB:**
    A very small variable-length binary large object.

11. **MEDIUMBLOB:**
    A medium-sized variable-length binary large object.

12. **LONGBLOB:**
    A long variable-length binary large object.

13. **ENUM('value1', 'value2', ...):**
    Enumerated type, representing one of a predefined set of values.

14. **SET('value1', 'value2', ...):**
    Set type, representing a collection of values chosen from a predefined set.


`💀 Number Data Types`

1. **INTEGER or INT:**
   Represents whole numbers.

2. **TINYINT:**
   A very small integer.

3. **SMALLINT:**
   Small-sized integer.

4. **MEDIUMINT:**
   Medium-sized integer.

5. **BIGINT:**
   Large-sized integer.

6. **DECIMAL(p, s) or NUMERIC(p, s):**
   Fixed-point decimal numbers with precision (total digits) and scale (decimal places).

7. **FLOAT(p):**
   Floating-point number with single-precision.

8. **DOUBLE(p):**
   Floating-point number with double-precision.

9. **REAL:**
   A synonym for DOUBLE.

10. **BIT(n):**
    A bit-field type, representing a fixed number of bits.

`💀 Date-Time Data Types`

In MySQL, the specific date and time data types include:

1. **DATE:**
   Represents a date in the format YYYY-MM-DD.

2. **TIME:**
   Represents a time of day in the format HH:MM:SS.

3. **DATETIME:**
   Represents a combination of date and time in the format YYYY-MM-DD HH:MM:SS.

4. **TIMESTAMP:**
   Similar to DATETIME but with a narrower range and automatically converts to the current timestamp on insert or update.

5. **YEAR:**
   Represents a four-digit year value.

# Inserting-Data

## Inserting Single Row

    Syntax:

        INSERT INTO table_name 
        (column1, column2, column3, ...)
        VALUES 
        (value1, value2, value3, ...);

    Example:

        INSERT INTO users 
        (id, name, email, password, contact, address, dob, gender, status)
        VALUES 
        (1, 'John Doe', 'john@example.com', 'hashed_password', '+123456789', '123 Main St, City', '1990-01-15', 'M', 1);

## Inserting Multiple Rows

    Syntax:

        INSERT INTO table_name 
        (column1, column2, column3, ...)
        VALUES 
        (value1, value2, value3, ...),
        (value1, value2, value3, ...),
        (value1, value2, value3, ...)

    Example:

        INSERT INTO users 
        (id, name, email, password, contact, address, dob, gender, status)
        VALUES
        (2, 'Jane Smith', 'jane@example.com', 'hashed_password2', '+987654321', '456 Oak St, Town', '1995-03-22', 'F', 1),
        (3, 'Alex Johnson', 'alex@example.com', 'hashed_password3', '+1122334455', '789 Pine St, Village', '1988-07-10', 'M', 0),
        (4, 'Avery Taylor', 'avery@example.com', 'hashed_password4', '+9988776655', '321 Elm St, City', '2000-09-05', 'O', 1),
        (5, 'Chris Anderson', 'chris@example.com', 'hashed_password5', '+1122334466', '567 Birch St, Town', '1992-12-18', 'M', 0),
        (6, 'Taylor Davis', 'taylor@example.com', 'hashed_password6', '+1122334477', '876 Maple St, Village', '1985-05-30', 'F', 1);

![Screenshot (2660)](https://github.com/k-sameer701/Learn-SQL/assets/103239208/2a40d253-4d40-4af2-8091-e3833db1cc21)

# Select-And-Where

## SELECT Statement

`In MySQL, you use the SELECT statement to retrieve data from one or more tables. `

    Syntax:

        SELECT column1, column2, ...
        FROM table_name;

    Example:

        SELECT name, email
        FROM users;


    If you want to select all columns from a table, you can use the wildcard *

    Syntax:

        SELECT *
        FROM table_name;

    Example:

        SELECT *
        FROM users;

## WHERE Clause

`The WHERE clause is used to filter records.`

`It is used to extract only those records that fulfill a specified condition.`

    Syntax:

        SELECT column1, column2, ...
        FROM table_name
        WHERE condition

    Example:
        
        SELECT id, name, email
        FROM users
        WHERE gender = 'M' AND status = 1;

## WHERE Conditions

`In SQL, the WHERE clause is used to filter the rows returned by a query based on specified conditions. Here are common conditions that can be used in conjunction with the WHERE clause:`

1. **Equality (`=`):**
   - Used to filter rows where a specified column is equal to a specific value.
   - Example: `WHERE column_name = value;`

2. **Inequality (`!=` or `<>`):**
   - Used to filter rows where a specified column is not equal to a specific value.
   - Example: `WHERE column_name <> value;`

3. **Comparison Operators (`<`, `>`, `<=`, `>=`):**
   - Used to filter rows based on numerical or date comparisons.
   - Example: `WHERE column_name > value;`

4. **LIKE Operator:**
   - Used to perform pattern matching with wildcard characters (`%` for any sequence of characters, `_` for a single character).
   - Example: `WHERE column_name LIKE 'pattern';`

5. **BETWEEN Operator:**
   - Used to filter rows within a specified range.
   - Example: `WHERE column_name BETWEEN value1 AND value2;`

6. **IN Operator:**
   - Used to filter rows where a column matches any value in a specified list.
   - Example: `WHERE column_name IN (value1, value2, ...);`

7. **IS NULL and IS NOT NULL:**
   - Used to filter rows where a column is (or is not) NULL.
   - Example: `WHERE column_name IS NULL;`

8. **Logical Operators (AND, OR, NOT):**
   - Used to combine multiple conditions.
   - Example: `WHERE condition1 AND condition2;`

9. **EXISTS Operator:**
   - Used to check if a subquery returns any results.
   - Example: `WHERE EXISTS (SELECT * FROM another_table WHERE condition);`

10. **ANY and ALL Operators:**
    - Used with subqueries for comparing values.
    - Example: `WHERE column_name > ANY (SELECT column_name FROM another_table);`

## ALIAS

`In SQL, an alias is a temporary name. It is used to provide a more readable or meaningful name to a table or column, especially when dealing with complex queries or when working with the result of a query.`

There are two main types of aliases:

1. **Table Alias:**
   - Used to give a table a temporary, alternative name in a query.

   - Syntax:
     
            SELECT column1, column2, ...
            FROM table_name AS alias_name
            WHERE condition;
     
   - Example:
     
            SELECT name, id
            FROM users AS Active_Users
            WHERE status = 1;

2. **Column Alias:**
   - Used to assign a temporary name to a column in the result set.
   
   - Syntax:
     
            SELECT column_name AS alias_name, ...
            FROM table_name
            WHERE condition;
            
   - Example:
     
            SELECT name AS E_Name, id AS U_ID
            FROM users 
            WHERE status = 1;
     
# Constraints

## Table Constraints

![Screenshot (2661)-1](https://github.com/k-sameer701/Learn-SQL/assets/103239208/2ffa2d83-07c7-4a09-9603-86e0e1d516cb)


In MySQL, table constraints are rules or conditions applied to the columns in a table to maintain the integrity, accuracy, and relationships of the data. 
They are specified during the table creation using the `CREATE TABLE` statement. Constraints can also be added or modified later using the `ALTER TABLE` statement.

1. **PRIMARY KEY Constraint:**
   - Ensures that a column or a combination of columns uniquely identifies each row in the table.
   - Example:
     
            CREATE TABLE employees (
                employee_id INT PRIMARY KEY,
                first_name VARCHAR(50),
                last_name VARCHAR(50)
            );

            

2. **FOREIGN KEY Constraint:**
   - Establishes a link between two tables, enforcing referential integrity.
   - Example:
     
            CREATE TABLE orders (
                order_id INT PRIMARY KEY,
                customer_id INT,
                FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
            );
            

3. **UNIQUE Constraint:**
   - Ensures that all values in a column (or a combination of columns) are unique.
   - Example:
     
            CREATE TABLE products (
                product_name VARCHAR(100) UNIQUE,
                price DECIMAL(10, 2)
            );

            

4. **CHECK Constraint:**
   - Specifies a condition that must be satisfied for each row in the table.
   - Example:
     
            CREATE TABLE employees (
                employee_id INT,
                salary DECIMAL(10, 2) CHECK (salary >= 0)
            );
            

5. **DEFAULT Constraint:**
   - Provides a default value for a column if no value is specified during an INSERT operation.
   - Example:
     
            CREATE TABLE students
            (
                id INT NOT NULL UNIQUE,
                name VARCHAR(100) NOT NULL,
                email VARCHAR(150) NOT NULL UNIQUE,
                age TINYINT CHECK (age >= 18),
                status BOOLEAN DEFAULT 1
            );
            

6. **NOT NULL Constraint:**
   - Ensures that a column cannot have a NULL value.
   - Example:
     
            CREATE TABLE orders (
                order_id INT,
                order_date DATE NOT NULL
            );




