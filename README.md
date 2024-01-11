# MySql-CheatSheet

## ⛄ Table of Content

* [1. Introduction](#Introduction)
* [2. Database-Table](#Database-Table)
* [3. Inserting-Data](#Inserting-Data)

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


