# Experiment 5

## AIM
To perform aggregate functions and use SQL functions on the Employee table to calculate totals, averages, maximum, minimum, and string operations.

## THEORY
Aggregate functions in SQL are used to perform calculations on a group of rows and return a single value. Common aggregate functions include:

- COUNT(): Counts number of records
- SUM(): Calculates total
- MAX(): Finds maximum value
- MIN(): Finds minimum value
- AVG(): Finds average value

SQL also provides string functions such as:
- UPPER(): Converts text to uppercase
- LOWER(): Converts text to lowercase
- INITCAP(): Converts text to proper case
- LENGTH(): Finds length of a string

These functions help in analyzing and summarizing data efficiently.

This experiment demonstrates the use of aggregate and string functions on employee data. :contentReference[oaicite:0]{index=0}

## QUESTION
1. Display total number of employees.  
2. Display total salary of all employees.  
3. Display maximum salary.  
4. Display minimum salary.  
5. Display average salary.  
6. Display maximum salary of clerks.  
7. Display maximum salary in department 20.  
8. Display minimum salary of salesman.  
9. Display average salary of managers.  
10. Display total salary of analysts in department 40.  
11. Display employee names in uppercase.  
12. Display employee names in lowercase.  
13. Display employee names in proper case.  
14. Display length of your name.  
15. Display length of all employee names.  

## QUERY
```sql
-- 1. Total number of employees
SELECT COUNT(*) FROM Employee;

-- 2. Total salary
SELECT SUM(SAL) FROM Employee;

-- 3. Maximum salary
SELECT MAX(SAL) FROM Employee;

-- 4. Minimum salary
SELECT MIN(SAL) FROM Employee;

-- 5. Average salary
SELECT AVG(SAL) FROM Employee;

-- 6. Maximum salary of clerks
SELECT MAX(SAL) FROM Employee
WHERE JOB = 'CLERK';

-- 7. Maximum salary in Dept 20
SELECT MAX(SAL) FROM Employee
WHERE DeptNo = 20;

-- 8. Minimum salary of salesman
SELECT MIN(SAL) FROM Employee
WHERE JOB = 'SALESMAN';

-- 9. Average salary of managers
SELECT AVG(SAL) FROM Employee
WHERE JOB = 'MANAGER';

-- 10. Total salary of analysts in Dept 40
SELECT SUM(SAL) FROM Employee
WHERE JOB = 'ANALYST' AND DeptNo = 40;

-- 11. Names in uppercase
SELECT UPPER(ENAME) FROM Employee;

-- 12. Names in lowercase
SELECT LOWER(ENAME) FROM Employee;

-- 13. Names in proper case
SELECT INITCAP(ENAME) FROM Employee;

-- 14. Length of your name
SELECT LENGTH('YOUR_NAME') FROM DUAL;

-- 15. Length of employee names
SELECT ENAME, LENGTH(ENAME) FROM Employee;