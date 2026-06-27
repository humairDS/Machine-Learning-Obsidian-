==Creating our First SQL DATABASE

Our first SQL Query

creating database:
```SQL
CREATE DATABASE College;
```
dropping or deleting database:
```SQL 
DROP DATABASE College;
```
using database:
```SQL
USE College;
```


==Creating Our First SQL Table

```SQL 
CREATE TABLE student (
	id INT PRIMARY KEY,
	name VARCHAR(50),
	age INT NOT NULL
);
```
==Inserting Data Into the TABLE
```SQL 
INSERT INTO student VALUES(1,"UMAIR",26);
INSERT INTO student VALUES(2,"SUNDUS",24)
```

==Print the TABLE

```SQL
SELECT * FROM student;
```




## SQL Datatypes 


| DATATYPE |                            DESCRIPTION                             |    USAGE    |
| :------: | :----------------------------------------------------------------: | :---------: |
|   CHAR   |         string(0,255),can store characters of fixed lenght         |  CHAR(50)   |
| VARCHAR  |       string(0,255),can stire characters up to guven length        | VARCHAR(50) |
|   BLOB   |           string(0,65535),can store binary large object            | BLOB(1000)  |
|   INT    |             interger(-2,147,483,648 to 2,147,483,647)              |     INT     |
| TINYINT  |                        integer(-128 to 127)                        |   TINYINT   |
|  BIGINT  |                              interger                              |   BIGINT    |
|   BIT    |          can store x-bit values, x can range from 1 to 64          |   BIT(2)    |
|  FLOAT   |            Decimal number - with precision to 23 digits            |    FLOAT    |
|  DOUBLE  |               Decimal Number - with 24 to 53 digits                |   DOUBLE    |
| BOOLEAN  |                        Boolean Values 0 -1                         |   BOOLEAN   |
|   DATE   | date in format of YYYY-MM-DD ranging from 1000-01-01 to 9999-12-31 |    DATE     |
|   YEAR   |         year in 4 Digits format ranging from 1901 to 2155          |    YEAR     |


==Signed & Unsigned

```SQL
TINYINT UNSIGNED (0 to 255)
```


## Types of SQL Commands

**DDL(Data Definition Language)**:==create==, ==alter==, ==rename==, ==truncate== & ==drop==
**DQL (Data Query Language)**: ==select==
**DML(Data Manipulation Language)**:         , ==insert==, ==update== & ==delete==
**DCL(Data Control Language)**: ==grant & revoke permission to users==
**TCL(Transaction Control Language)**:==start transaction, commit, rollback== 

## Database related Queries 
```SQL 
CREATE DATABASE db_name;
CREATE DATABASE IF NOT EXISTS db_name;
CREATE DATABASE IF NOT EXISTS college;

DROP DATABASE db_name;
DROP DATABASE IF EXISTS db_name;

SHOW DATABASES;
SHOW TABLES; 
```

TABLE related Queries
1. Select and View all rows and column
```SQL 
SELECT * FROM table_name;
```
==note:==   * means select all rows and columns 


2. Insert
```SQL 
INSERT INTO table_name
(colname1,coname2)
VALUES
(col1_v1,col_v1),
(col1_v2,col2_v2);
```


[[SQL PRATICE QUESTIONS]] 

## Keys 

==Primary Key

```
it is a column (or set in columns) in a table that uniquely identifies each row. (a unique id)
There is Only 1 PK & it should be NOT null
```

==Foreign Key 

```
A Foreign Key is a column (or set of columns) in a table that refers to the primary key 
There can be multiple FKs
FKs can have duplicate & null values.
```

## Constraints

SQL constraints are used to specify rule for data in a table.

==**NOT NULL**== : Columns cannot have a null value
```SQL
col1 int NOT NULL
```

==**UNIQUE**==: all values in columns are different 
```SQL 
col2 int UNIQUE
```

==**PRIMARY KEY**==: makes a column unique & not null but used only for one 
```SQL
id int PRIMARY KEY

CREATE TABLE temp(
id int not null
PRIMARY KEY (id)
);
```


==**FOREIGN KEY**==: prevent actions that would destroy links between tables
```SQL 
CREATE TABLE temp (
cust_id int,
FOREIGN KEY (cust_id) reference customer (id)
);
```

==**DEFAULT**== sets the default value of a column
```SQL 
salary INT DEFAULT 25000
```


==**CHECK**==: if can limit the values allowed in a column
```SQL 
CREATE TABLE city(
id INT PRIMARY KEY,
city VARCHAR(50),
age INT,
CONSTRAINT age_check CHECK (age>=18 AND city="DELHI")
);
```

```SQL 
CREATE TABLE newtab (
age INT CHECK (age >= 18)
);
```



## Creating an Sample

Create this sample table 
```SQL 
CREATE DATABASE college;
USE college;

CREATE TABLE student (
	rollno INT PRIMARY KEY,
	name VARCHAR(50),
	marks INT NOT NULL,
	grade VARCHAR(1),
	city VARCHAR(20)
);
```

insert this data 
```SQL 
INSERT INTO student
(rollno,name,marks,grade,city)
VALUES 
(101,'umair',78,"A","KARACHI"),
(102,"sundus",80,"A","KARACHI"),
(101,'shaheer',60,"B","KARACHI"),
(102,"hamiz",91,"A","LAHORE"),
(101,'husban',50,"C","ISLAMABAD"),
(102,"sumbul",17,"F","MULTAN");
```



## SELECT 
used to select any data from the database

BASIC SYNTAX
```SQL
SELECT col1, col2 FROM table_name;
```

To Select ALL
```SQL 
SELECT * FROM table_name;
```

To see the unique
```SQL 
SELECT DISTINCT col_name FROM student;
```


## Where Clause

to define some conditions

```SQL 
SELECT col1,col2, FROM table_name
WHERE conditions;
```

```SQL
SELECT * FROM student WHERE marks >80;
```

							or 

```SQL 
SELECT *
FROM student 
WHERE marks>80;
```

**Using Operators in Where

==Arithmetic Operators==: +, - , * , / , %

==Comparison Operators==: =,!=,>,>=,<,<=

==Logical Operators==: AND,OR,NOT,IN,BETWEEN,ALL,LIKE,ANY

==Bitwise Operators==: & (Bitwise AND),| (Bitwise OR)



## Operators 

==Between== (selects for a given range)

```SQL 
SELECT * FROM student WHERE marks BETWEEN 80 AND 90;
```

==In==(matches any value in the list)

```SQL 
SELECT * FROM student WHERE city IN("DELHI","MUMBAI");
```

==NOT==(to negate the given condition)

```SQL 
SELECT * FROM student WHERE city NOT IN ("Delhi","Mumbai");
```



## Limit Clause 

Sets an upper limit on number of (tuples) rows to be returned 

```SQL 
SELECT * FROM student LIMIT 3;
```



## Order By Clause

to sort in ascending (ASC) or descending order (DESC)

```SQL 
SELECT *
FROM student
ORDER BY city ASC;
```


## Aggregate Functions

Aggregate functions peform a calculation on aset of values, and return a single value 

  COUNT()
  MAX()
  MIN()
  SUM()
  AVG()

Get maximum marks 
```SQL 
SELECT max(marks)
FROM student;
```

Get Average Marks 
```SQL 
SELECT avg(marks)
FROM student;
```


## Group By Clause
Groups rows that have the same values into summary rows.
It collects data from multiple records and groups the result by one or more column.

Generally we use group by with some aggregation functions.

Count number of students in each city
```SQL 
SELECT city, count(name)
FROM student
GROUP BY city;
```
 