# Experiment 3

## AIM
To retrieve and display data from the Employee table using sorting, pattern matching, and conditional queries.

## THEORY
SQL provides powerful features to retrieve and organize data using conditions and sorting techniques. The ORDER BY clause is used to sort data in ascending or descending order. Pattern matching can be done using the LIKE operator with wildcards such as '%' and '_'.

Logical operators like AND, OR, and NOT help in filtering records based on multiple conditions. Arithmetic operations can also be performed on columns while retrieving data.

This experiment focuses on applying these concepts to extract meaningful information from the Employee table. :contentReference[oaicite:0]{index=0}

## QUESTION
1. List all employees and jobs in Department 30 in descending order of salary.  
2. List job and department number of employees whose names are five letters long, begin with 'A' and end with 'N'.  
3. Display names of employees starting with 'S'.  
4. Display names of employees ending with 'S'.  
5. Display employees working in department 10, 20, or 40 or working as clerk, salesman, or analyst.  
6. Display employee number and names of employees who earn commission.  
7. Display employee number and total salary for each employee.  
8. Display employee number and annual salary for each employee.  
9. Display names of clerks earning more than 3000.  
10. Display names of clerks, salesmen, or analysts earning more than 3000.  

## QUERY
```sql
-- 1. Employees and jobs in Dept 30 sorted by salary (descending)
SELECT ENAME, JOB, SAL FROM Employee
WHERE DeptNo = 30
ORDER BY SAL DESC;

-- 2. Names with 5 letters, start with A and end with N
SELECT JOB, DeptNo FROM Employee
WHERE ENAME LIKE 'A___N';

-- 3. Names starting with S
SELECT ENAME FROM Employee
WHERE ENAME LIKE 'S%';

-- 4. Names ending with S
SELECT ENAME FROM Employee
WHERE ENAME LIKE '%S';

-- 5. Employees in Dept 10, 20, 40 or specific jobs
SELECT * FROM Employee
WHERE DeptNo IN (10, 20, 40)
   OR JOB IN ('CLERK', 'SALESMAN', 'ANALYST');

-- 6. Employees earning commission
SELECT EMPNO, ENAME FROM Employee
WHERE COMM IS NOT NULL;

-- 7. Employee number and total salary
SELECT EMPNO, (SAL + NVL(COMM,0)) AS TOTAL_SAL FROM Employee;

-- 8. Employee number and annual salary
SELECT EMPNO, (SAL * 12) AS ANNUAL_SAL FROM Employee;

-- 9. Clerks earning more than 3000
SELECT ENAME FROM Employee
WHERE JOB = 'CLERK' AND SAL > 3000;

-- 10. Clerks, salesmen, or analysts earning more than 3000
SELECT ENAME FROM Employee
WHERE JOB IN ('CLERK', 'SALESMAN', 'ANALYST')
AND SAL > 3000;