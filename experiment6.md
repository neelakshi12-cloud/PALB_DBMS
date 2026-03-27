# Experiment 6

## AIM
To perform SQL queries using date functions, conversion functions, and formatting functions.

## THEORY
SQL provides various built-in functions to work with dates, numbers, and strings.

- **Date Functions**: Used to manipulate and format dates (SYSDATE, ADD_MONTHS, NEXT_DAY).
- **Conversion Functions**: Used to convert data types (TO_CHAR).
- **DECODE Function**: Used to display values conditionally.
- **Arithmetic Operations on Dates**: Used to calculate age, duration, etc.

These functions help in formatting output and performing real-world calculations such as age, joining dates, and time.

This experiment demonstrates the use of such functions on the Employee table. :contentReference[oaicite:0]{index=0}

## QUESTION
1. Display empno, ename, deptno with department name using DECODE.  
2. Display your age in days.  
3. Display your age in months.  
4. Display current date in formatted style.  
5. Display joining message of employees.  
6. Find nearest Saturday after current date.  
7. Display current time.  
8. Display date three months before current date.  
9. Display employees who joined in December.  
10. Display employees with string manipulation on hiredate and salary.  
11. Display employees whose 10% salary equals joining year.  
12. Display employees who joined before 15th of month.  
13. Display employees whose joining date condition matches deptno.  

## QUERY
```sql
-- 1. Display dept name using DECODE
SELECT EMPNO, ENAME,
DECODE(DeptNo,
       10, 'RESEARCH',
       20, 'ACCOUNTING',
       30, 'SALES',
       40, 'OPERATIONS') AS DEPT_NAME
FROM Employee;

-- 2. Age in days
SELECT (SYSDATE - TO_DATE('01-JAN-2000','DD-MON-YYYY')) AS AGE_IN_DAYS FROM DUAL;

-- 3. Age in months
SELECT MONTHS_BETWEEN(SYSDATE, TO_DATE('01-JAN-2000','DD-MON-YYYY')) AS AGE_IN_MONTHS FROM DUAL;

-- 4. Current date formatted
SELECT TO_CHAR(SYSDATE, 'DDth Month Day YYYY') FROM DUAL;

-- 5. Employee joining message
SELECT ENAME || ' has joined on ' || TO_CHAR(HIREDATE, 'Day DDth Month YYYY')
FROM Employee;

-- 6. Nearest Saturday
SELECT NEXT_DAY(SYSDATE, 'SATURDAY') FROM DUAL;

-- 7. Current time
SELECT TO_CHAR(SYSDATE, 'HH:MI:SS AM') FROM DUAL;

-- 8. Date three months before
SELECT ADD_MONTHS(SYSDATE, -3) FROM DUAL;

-- 9. Employees joined in December
SELECT ENAME FROM Employee
WHERE TO_CHAR(HIREDATE, 'MON') = 'DEC';

-- 10. String manipulation
SELECT ENAME, SUBSTR(HIREDATE,1,2) || SUBSTR(SAL,-2)
FROM Employee;

-- 11. 10% salary equals joining year
SELECT ENAME FROM Employee
WHERE (SAL * 0.10) = TO_NUMBER(TO_CHAR(HIREDATE, 'YYYY'));

-- 12. Joined before 15th of month
SELECT ENAME, HIREDATE FROM Employee
WHERE TO_CHAR(HIREDATE, 'DD') < 15;

-- 13. Joining date condition matches deptno
SELECT ENAME FROM Employee
WHERE TO_CHAR(HIREDATE, 'DD') = DeptNo;