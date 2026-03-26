# Experiment 2

## AIM
To retrieve data from the Employee table using various SQL SELECT queries with conditions.

## THEORY
Data retrieval is one of the most important operations in DBMS. It is done using the SELECT statement in SQL. The SELECT query allows users to fetch specific data from a table based on conditions.

Common clauses used:
- SELECT: To choose columns
- WHERE: To apply conditions
- DISTINCT: To remove duplicate values
- AND, OR: To combine conditions
- BETWEEN: To specify a range
- LIKE: For pattern matching

In this experiment, different queries are applied on the Employee table to retrieve meaningful information. :contentReference[oaicite:0]{index=0}

## QUESTION
1. List all distinct jobs in Employee.  
2. List all information about employees in Department 30.  
3. Find department numbers greater than 20.  
4. Find all managers and clerks in Department 30.  
5. List employee name, number, and department of all clerks.  
6. Find all managers not in Department 30.  
7. List employees in Department 10 who are not managers or clerks.  
8. Find employees earning between 1200 and 1400.  
9. List employees who are clerks, analysts, or salesmen.  
10. List employees whose names begin with M.  

## QUERY
```sql
-- 1. List all distinct jobs
SELECT DISTINCT JOB FROM Employee;

-- 2. Employees in Department 30
SELECT * FROM Employee
WHERE DeptNo = 30;

-- 3. Department numbers greater than 20
SELECT DISTINCT DeptNo FROM Employee
WHERE DeptNo > 20;

-- 4. Managers and clerks in Department 30
SELECT * FROM Employee
WHERE DeptNo = 30 AND (JOB = 'MANAGER' OR JOB = 'CLERK');

-- 5. Name, number, department of clerks
SELECT ENAME, EMPNO, DeptNo FROM Employee
WHERE JOB = 'CLERK';

-- 6. Managers not in Department 30
SELECT * FROM Employee
WHERE JOB = 'MANAGER' AND DeptNo <> 30;


-- 7. Employees in Dept 10 not manager or clerk
SELECT * FROM Employee
WHERE DeptNo = 10 AND JOB NOT IN ('MANAGER', 'CLERK');

-- 8. Employees earning between 1200 and 1400
SELECT ENAME, JOB, SAL FROM Employee
WHERE SAL BETWEEN 1200 AND 1400;

-- 9. Clerks, analysts, or salesmen
SELECT ENAME, DeptNo FROM Employee
WHERE JOB IN ('CLERK', 'ANALYST', 'SALESMAN');

-- 10. Names starting with M
SELECT ENAME, DeptNo FROM Employee
WHERE ENAME LIKE 'M%';