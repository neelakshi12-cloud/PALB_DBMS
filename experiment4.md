# Experiment 4

## AIM
To perform SQL queries using date functions, string functions, arithmetic operations, and conditional updates on the Employee table.

## THEORY
SQL provides various functions to manipulate data such as:

- **Date Functions**: Used to handle and compare dates (e.g., SYSDATE).
- **String Functions**: Used for pattern matching and text operations (e.g., LIKE, LENGTH).
- **Arithmetic Operations**: Used to calculate values like salary, increments, etc.
- **UPDATE**: Used to modify existing data in the table.

These functions help in extracting meaningful insights and modifying data effectively in a database.

This experiment demonstrates the use of these functions on employee data. :contentReference[oaicite:0]{index=0}

## QUESTION
1. Display employees who joined before 30-June-80 or after 31-Dec-81.  
2. Display employees whose second letter is 'A'.  
3. Display employees whose name is exactly 5 characters long.  
4. Display employees whose second letter is 'A'.  
5. Display employees not working as salesman, clerk, or analyst.  
6. Display employee name with annual salary sorted by highest salary.  
7. Display name, sal, hra, da, pf, totalsal.  
8. Update salary by 10% for employees not eligible for commission.  
9. Display employees whose salary is more than 3000 after 20% increment.  
10. Display employees whose salary has at least 3 digits.  

## QUERY
```sql
-- 1. Employees joined before 30-June-80 or after 31-Dec-81
SELECT ENAME, HIREDATE FROM Employee
WHERE HIREDATE < '30-JUN-80' OR HIREDATE > '31-DEC-81';

-- 2. Second letter is 'A'
SELECT ENAME FROM Employee
WHERE ENAME LIKE '_A%';

-- 3. Name exactly 5 characters
SELECT ENAME FROM Employee
WHERE LENGTH(ENAME) = 5;

-- 4. Second letter is 'A' (repeated)
SELECT ENAME FROM Employee
WHERE ENAME LIKE '_A%';

-- 5. Not salesman, clerk, or analyst
SELECT ENAME, JOB FROM Employee
WHERE JOB NOT IN ('SALESMAN', 'CLERK', 'ANALYST');

-- 6. Name with annual salary (highest first)
SELECT ENAME, (SAL * 12) AS ANNUAL_SAL FROM Employee
ORDER BY ANNUAL_SAL DESC;

-- 7. Salary breakdown
SELECT ENAME, SAL,
       (SAL * 0.15) AS HRA,
       (SAL * 0.10) AS DA,
       (SAL * 0.05) AS PF,
       (SAL + (SAL*0.15) + (SAL*0.10) - (SAL*0.05)) AS TOTAL_SAL
FROM Employee;

-- 8. Update salary by 10% where no commission
UPDATE Employee
SET SAL = SAL + (SAL * 0.10)
WHERE COMM IS NULL;

-- 9. Salary > 3000 after 20% increment
SELECT ENAME, SAL FROM Employee
WHERE (SAL + (SAL * 0.20)) > 3000;

-- 10. Salary with at least 3 digits
SELECT ENAME, SAL FROM Employee
WHERE SAL >= 100;