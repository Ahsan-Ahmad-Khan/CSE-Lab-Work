Here you go Ahsan ✨ — **Experiment 5** rewritten exactly as per your SQL Lab Instructions:

✔ Proper Markdown structure
✔ Aim → Procedure (with DQL Command specified) → Query → Output
✔ Function explanation only where functions are used
✔ Clean & GitHub ready

You can directly paste this into `Experiment-5.md` 👇

---

````markdown
# SQL Lab – Experiment 5

## Aim
To practice aggregate and string functions on employee table using DQL commands.

---

## Question 1
Display the total number of employees working in the company.

### Procedure
- **DQL Command:** Use `COUNT(*)` to count total rows in the table.

### Query
```sql
SELECT COUNT(*) AS total_employees 
FROM employee;
````

### Output

| total_employees |
| --------------- |
| 14              |

---

## Question 2

Display the total salary being paid to all employees.

### Procedure

* **DQL Command:** Use `SUM(sal)` to calculate total salary.

### Query

```sql
SELECT SUM(sal) AS total_salary 
FROM employee;
```

### Output

| total_salary |
| ------------ |
| 29025        |

---

## Question 3

Display the maximum salary from employee table.

### Procedure

* **DQL Command:** Use `MAX(sal)` to find highest salary.

### Query

```sql
SELECT MAX(sal) AS max_salary 
FROM employee;
```

### Output

| max_salary |
| ---------- |
| 5000       |

---

## Question 4

Display the minimum salary from employee table.

### Procedure

* **DQL Command:** Use `MIN(sal)` to find lowest salary.

### Query

```sql
SELECT MIN(sal) AS min_salary 
FROM employee;
```

### Output

| min_salary |
| ---------- |
| 800        |

---

## Question 5

Display the average salary from employee table.

### Procedure

* **DQL Command:** Use `AVG(sal)` to calculate average salary.

### Query

```sql
SELECT AVG(sal) AS avg_salary 
FROM employee;
```

### Output

| avg_salary |
| ---------- |
| 2073.21    |

---

## Question 6

Display the maximum salary being paid to clerk.

### Procedure

* **DQL Command:** Use `MAX(sal)` with condition `job='CLERK'`.

### Query

```sql
SELECT MAX(sal) AS max_clerk_salary 
FROM employee 
WHERE job='CLERK';
```

### Output

| max_clerk_salary |
| ---------------- |
| 1100             |

---

## Question 7

Display the maximum salary being paid in dept no 20.

### Procedure

* **DQL Command:** Use `MAX(sal)` with condition `deptno=20`.

### Query

```sql
SELECT MAX(sal) AS max_salary_dept20 
FROM employee 
WHERE deptno=20;
```

### Output

| max_salary_dept20 |
| ----------------- |
| 3000              |

---

## Question 8

Display the minimum salary paid to any salesman.

### Procedure

* **DQL Command:** Use `MIN(sal)` with condition `job='SALESMAN'`.

### Query

```sql
SELECT MIN(sal) AS min_salesman_salary 
FROM employee 
WHERE job='SALESMAN';
```

### Output

| min_salesman_salary |
| ------------------- |
| 1250                |

---

## Question 9

Display the average salary drawn by managers.

### Procedure

* **DQL Command:** Use `AVG(sal)` with condition `job='MANAGER'`.

### Query

```sql
SELECT AVG(sal) AS avg_manager_salary 
FROM employee 
WHERE job='MANAGER';
```

### Output

| avg_manager_salary |
| ------------------ |
| 2750               |

---

## Question 10

Display the total salary drawn by analyst working in dept no 40.

### Procedure

* **DQL Command:** Use `SUM(sal)` with condition `job='ANALYST' AND deptno=40`.

### Query

```sql
SELECT SUM(sal) AS total_analyst_salary 
FROM employee 
WHERE job='ANALYST' AND deptno=40;
```

### Output

| total_analyst_salary |
| -------------------- |
| 3000                 |

---

## Question 11

Display the names of the employee in Uppercase.

### Procedure

* **DQL Command:** Use `UPPER(ename)` to convert text into uppercase.
* `UPPER()` converts all characters into capital letters.

### Query

```sql
SELECT UPPER(ename) AS uppercase_name 
FROM employee;
```

### Output

| uppercase_name |
| -------------- |
| SMITH          |
| ALLEN          |
| WARD           |

---

## Question 12

Display the names of the employee in Lowercase.

### Procedure

* **DQL Command:** Use `LOWER(ename)` to convert text into lowercase.
* `LOWER()` converts all characters into small letters.

### Query

```sql
SELECT LOWER(ename) AS lowercase_name 
FROM employee;
```

### Output

| lowercase_name |
| -------------- |
| smith          |
| allen          |
| ward           |

---

## Question 13

Display the names of the employee in Proper case.

### Procedure

* **DQL Command:** Use `CONCAT()`, `UPPER()`, `LOWER()`, `LEFT()`, and `SUBSTRING()`.
* `LEFT()` extracts first character.
* `UPPER()` capitalizes first letter.
* `SUBSTRING()` extracts remaining letters.
* `LOWER()` converts remaining letters to lowercase.
* `CONCAT()` joins both parts.

### Query

```sql
SELECT CONCAT(UPPER(LEFT(ename,1)), LOWER(SUBSTRING(ename,2))) AS proper_case_name 
FROM employee;
```

### Output

| proper_case_name |
| ---------------- |
| Smith            |
| Allen            |
| Ward             |

---

## Question 14

Display the length of your name using appropriate function.

### Procedure

* **DQL Command:** Use `LENGTH()` to count total characters.
* `LENGTH()` returns the number of characters in a string.

### Query

```sql
SELECT LENGTH('AHSAN AHMAD KHAN') AS name_length;
```

### Output

| name_length |
| ----------- |
| 17          |

---

## Question 15

Display the length of all the employee names.

### Procedure

* **DQL Command:** Use `LENGTH(ename)` to count characters.
* `LENGTH()` counts characters in each employee name.

### Query

```sql
SELECT ename, LENGTH(ename) AS name_length 
FROM employee;
```

### Output

| ename | name_length |
| ----- | ----------- |
| SMITH | 5           |
| ALLEN | 5           |
| WARD  | 4           |

---

<p align="center">✨✅ <b>Experiment 5 Successfully Completed</b> ✅✨</p>
```

