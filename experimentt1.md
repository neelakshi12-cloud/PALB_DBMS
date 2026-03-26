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