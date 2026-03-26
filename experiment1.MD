<!-- # Experiment 1

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
```

![alt text](<output1.jpeg>)



DELETE FROM Employee_master
WHERE DeptNo = 10;

UPDATE Employee_master
SET SAL = SAL + (SAL * 0.10)
WHERE DeptNo = 20;

ALTER TABLE Employee_master
MODIFY SAL NUMBER(10,2);

DROP TABLE Employee_master;

 -->
# Experiment 1

## AIM
To create tables with given constraints and perform SQL operations including CREATE, DELETE, UPDATE, ALTER, and DROP on the Employee table.

## THEORY
A Database Management System (DBMS) helps in storing and managing data efficiently. In relational databases, data is stored in tables consisting of rows and columns.

SQL (Structured Query Language) is used to interact with the database. The main commands used in this experiment are:

- CREATE: To create tables
- DELETE: To remove records
- UPDATE: To modify data
- ALTER: To change table structure
- DROP: To delete table

The experiment uses Employee and Department tables to perform operations. :contentReference[oaicite:0]{index=0}

## QUESTION
1. Create Employee_master table with data using Employee table.  
2. Delete all records from Employee_master where DeptNo is 10.  
3. Update salary by 10% for employees in DeptNo 20.  
4. Alter SAL column to NUMBER(10,2).  
5. Drop Employee_master table.  

## QUERY
```sql
-- Create Employee_master table
CREATE TABLE Employee_master AS
SELECT * FROM Employee;

-- Delete records where DeptNo = 10
DELETE FROM Employee_master
WHERE DeptNo = 10;

-- Update salary with 10% increment for DeptNo = 20
UPDATE Employee_master
SET SAL = SAL + (SAL * 0.10)
WHERE DeptNo = 20;

-- Alter SAL column size
ALTER TABLE Employee_master
MODIFY SAL NUMBER(10,2);

-- Drop Employee_master table
DROP TABLE Employee_master;