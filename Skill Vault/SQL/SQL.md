http://www.r-5.org/files/books/computers/languages/sql/mysql/Alan_Beaulieu-Learning_SQL-EN.pdf

**Why Learn SQL?** 

If you are going to work with a relational database, whether you are writing applica-
tions, performing administrative tasks, or generating reports, you will need to know
how to interact with the data in your database. Even if you are using a tool that generates
SQL for you, such as a reporting tool, there may be times when you need to bypass the
automatic generation feature and write your own SQL statements.
Learning SQL has the added benefit of forcing you to confront and understand the data
structures used to store information about your organization. As you become com-
fortable with the tables in your database, you may find yourself proposing modifica-
tions or additions to your database schema.


We'll cover the book chapter by chapter.

|Chapter|Topic|Goal|
|---|---|---|
|1|Introduction to Databases & SQL|Understand what SQL is and why it exists|
|2|Creating & Populating Databases|Learn databases, tables, rows, columns|
|3|Query Primer|Learn `SELECT`|
|4|Filtering|`WHERE`, comparison operators|
|5|Querying Multiple Tables|JOINS|
|6|Working with Sets|UNION, INTERSECT, EXCEPT|
|7|Functions|String, numeric, date functions|
|8|Grouping|GROUP BY, HAVING|
|9|Subqueries|Nested queries|
|10|Advanced Joins|Self joins and more|
|11|Conditional Logic|CASE expressions|
|12|Transactions|COMMIT, ROLLBACK|
|13|Constraints & Indexes|Database design|
|14|Views|Virtual tables|
|15|Metadata|Information Schema|


# Before Chapter 1

Let's answer one question.
## What is Data?

Data is simply information.

Example:

| Student | Age | Marks |
| ------- | --- | ----- |
| Ali     | 20  | 87    |
| Ahmed   | 21  | 92    |
| Sara    | 19  | 81    |

This table is data.

---

## What is a Database?

A database is an organized collection of data.

Imagine your university has information about:

- Students
- Teachers
- Courses
- Departments
- Fees

Instead of keeping thousands of Excel files, everything is stored inside a **database**.

Think of it like this:

```
Database
│
├── Students Table
├── Courses Table
├── Teachers Table
├── Departments Table
└── Fees Table
```

A database contains many tables.

---

## What is a Table?

A table stores one type of information.

Example:

### Students Table

|Student_ID|Name|Age|
|---|---|---|
|1|Ali|20|
|2|Sara|19|
|3|Ahmed|21|

---

## Row (Record)

Each horizontal entry is called a **row**.

```
1 | Ali | 20
```

This row represents one student.

---

## Column (Field)

Each vertical category is called a **column**.

```
Student_IDNameAge
```

Each column describes one property.


##  **What is SQL?** 

SQL stands for:

**Structured Query Language**

SQL is the language we use to communicate with a database.

Just like:
- English → communicate with people
- Python → communicate with computers
- SQL → communicate with databases

## What can SQL do?

SQL allows us to:

- Read data
- Insert new data
- Update existing data
- Delete data
- Create tables
- Create databases
- Control permissions

## Example

Imagine a table:

|ID|Name|Age|
|---|---|---|
|1|Ali|20|
|2|Sara|19|
|3|Ahmed|21|


Suppose you only want the names.

You write:

```SQL
SELECT Name
FROM Students;
```

Result:

|Name|
|---|
|Ali|
|Sara|
|Ahmed|

You didn't manually search the table—SQL did it for you.

## Why Data Scientists Learn SQL

Most company data is stored in relational databases.

A typical workflow is:

```
Database
      ↓
     SQL      
      ↓
    Python (Pandas)
      ↓
   Machine Learning
      ↓
Visualization (Power BI/Tableau)
```

In many data-related jobs, you'll spend a significant amount of time using SQL to retrieve and prepare data before analyzing it in Python.

# SQL vs Python

| SQL                         | Python                                 |
| --------------------------- | -------------------------------------- |
| Retrieves data              | Analyzes data                          |
| Works directly on databases | Works on data after retrieval          |
| Declarative language        | General-purpose programming language   |
| Used with tables            | Used with variables, lists, DataFrames |

# Important Terms

- **Database** → Collection of tables
- **Table** → Collection of rows and columns
- **Row** → One record
- **Column** → One attribute
- **SQL** → Language used to interact with databases


[[SQL Questions]] 
1. [[SQL Chapter 1]]  
2. [[SQL Chapter 2]] 
