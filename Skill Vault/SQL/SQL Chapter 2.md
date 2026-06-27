
==Practical Beginning of SQL== 

Before writing SQL queries, we need a place where our data lives.

Think of it like this:

- Before writing Python code → You install Python.
- Before writing SQL queries → You install a Database Management System (DBMS).


# What is a DBMS?

A **Database Management System (DBMS)** is software that manages databases.

It is responsible for:

- Storing data
- Retrieving data
- Updating data
- Deleting data
- Ensuring data remains consistent
- Handling multiple users simultaneously

You don't interact directly with the database files. Instead, you send SQL commands to the DBMS, and it does the work.


# Popular DBMSs

There are many database systems, but they all use SQL (with some differences).

| DBMS                 | Used By                     | Free?                 |
| -------------------- | --------------------------- | --------------------- |
| MySQL                | Web applications, learning  | ✅ Yes                 |
| PostgreSQL           | Data Science, analytics     | ✅ Yes                 |
| SQLite               | Mobile apps, small projects | ✅ Yes                 |
| Microsoft SQL Server | Enterprises                 | Limited free editions |
| Oracle Database      | Large organizations         | Limited free editions |

# Which One Should We Use?

Since we're following **Alan Beaulieu's** book, we'll use **MySQL** because the examples in the book are written for it.

### We will install:

- **MySQL Community Server** (the database server)
- **MySQL Workbench** (a graphical interface to write and run SQL)

Think of them like this:

```
MySQL Server
      │
Stores the databases
      │
      ▼
MySQL Workbench
      │
You type SQL here
      │     
      ▼
Results are displayed
```

