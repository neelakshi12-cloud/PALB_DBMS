# Experiment 1

## AIM
To create tables with given constraints, insert records into the tables, and perform basic SQL operations such as CREATE, DELETE, UPDATE, ALTER, and DROP.

## THEORY
A Database Management System (DBMS) is used to store, manage, and retrieve data efficiently. In relational databases, data is organized into tables consisting of rows (tuples) and columns (attributes).

SQL (Structured Query Language) is used to perform operations on databases. Some important SQL commands include:

- **CREATE TABLE** – Used to create a new table in the database.
- **INSERT INTO** – Used to insert records into a table.
- **DELETE** – Used to remove records from a table.
- **UPDATE** – Used to modify existing records.
- **ALTER TABLE** – Used to modify the structure of a table.
- **DROP TABLE** – Used to delete an entire table.

In this experiment, two tables are used:
1. **EMPLOYEE**
2. **DEPARTMENT**

The EMPLOYEE table contains details such as employee number, name, job, manager, salary, commission, and department number. The DEPARTMENT table stores department numbers and department names. :contentReference[oaicite:0]{index=0}

## QUESTION

1. Create `Employee_master` table with data using `Employee` table.  
2. Delete all records from `Employee_master` whose `DeptNo` is 10.  
3. Update 10% increment in salary of employees whose `DeptNo` is 20 in `Employee_master`.  
4. Alter the `SAL` column with size `10,2` in `Employee_master`.  
5. Drop the `Employee_master` table.

## QUERY

### 1. Create Employee_master table
```sql
CREATE TABLE Employee_master AS
SELECT * FROM Employee;

![alt text] (<c:\Users\Neelakshi\OneDrive\Desktop\output1.jpeg>)
