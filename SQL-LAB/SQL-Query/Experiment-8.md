Perfect Ahsan 🔥✨
Here is your **Experiment 8** in the exact same clean Markdown format (Aim → Procedure → Query → Output).
All are **JOIN queries**, properly structured and MariaDB compatible.

You can directly paste this into `Experiment-8.md` 👇

---

````markdown
# SQL Lab – Experiment 8

## Aim
To practice SQL Joins (INNER JOIN, LEFT JOIN, SELF JOIN) and aggregate functions in MariaDB.

---

## Question 1
Display all employees with their department name.

### Procedure
- **DQL Command:** Use `INNER JOIN`.
- Join `employee` table with `department` table using `deptno`.

### Query
```sql
SELECT e.ename, d.dname
FROM employee e
INNER JOIN department d
ON e.deptno = d.deptno;
````

### Output

| ename | dname      |
| ----- | ---------- |
| SMITH | RESEARCH   |
| KING  | ACCOUNTING |

---

## Question 2

Display those employees whose manager name is JONES and also display their manager name.

### Procedure

* **DQL Command:** Use `SELF JOIN`.
* Join employee table with itself using `mgr`.

### Query

```sql
SELECT e.ename AS employee,
       m.ename AS manager
FROM employee e
JOIN employee m
ON e.mgr = m.empno
WHERE m.ename = 'JONES';
```

### Output

| employee | manager |
| -------- | ------- |
| SCOTT    | JONES   |

---

## Question 3

Display employee name, job, dept name, manager name and grade department wise.

### Procedure

* **DQL Command:** Use multiple joins.
* Join `employee`, `department`, `salgrade`, and self join for manager.

### Query

```sql
SELECT e.ename,
       e.job,
       d.dname,
       m.ename AS manager,
       s.grade
FROM employee e
JOIN department d ON e.deptno = d.deptno
LEFT JOIN employee m ON e.mgr = m.empno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
ORDER BY d.dname;
```

### Output

| ename | job   | dname    | manager | grade |
| ----- | ----- | -------- | ------- | ----- |
| SMITH | CLERK | RESEARCH | FORD    | 1     |

---

## Question 4

List employee name, job, salary grade and department name except 'CLERK'. Sort by highest salary.

### Procedure

* **DQL Command:** Use JOIN + WHERE + ORDER BY.

### Query

```sql
SELECT e.ename,
       e.job,
       s.grade,
       d.dname,
       e.sal
FROM employee e
JOIN department d ON e.deptno = d.deptno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
WHERE e.job <> 'CLERK'
ORDER BY e.sal DESC;
```

### Output

| ename | job       | grade | dname      | sal  |
| ----- | --------- | ----- | ---------- | ---- |
| KING  | PRESIDENT | 5     | ACCOUNTING | 5000 |

---

## Question 5

Display employee name, job and manager. Also display employees without manager.

### Procedure

* **DQL Command:** Use `LEFT JOIN`.

### Query

```sql
SELECT e.ename,
       e.job,
       IFNULL(m.ename,'No Manager') AS manager
FROM employee e
LEFT JOIN employee m
ON e.mgr = m.empno;
```

### Output

| ename | job       | manager    |
| ----- | --------- | ---------- |
| KING  | PRESIDENT | No Manager |

---

## Question 6

List employee name, job, annual salary, deptno, dept name and grade who earn 36000 a year or who are not clerks.

### Procedure

* **DQL Command:** Use condition with OR.

### Query

```sql
SELECT e.ename,
       e.job,
       e.sal*12 AS annual_salary,
       e.deptno,
       d.dname,
       s.grade
FROM employee e
JOIN department d ON e.deptno = d.deptno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
WHERE e.sal*12 = 36000
   OR e.job <> 'CLERK';
```

### Output

| ename | job     | annual_salary | deptno | dname    | grade |
| ----- | ------- | ------------- | ------ | -------- | ----- |
| SCOTT | ANALYST | 36000         | 20     | RESEARCH | 4     |

---

## Question 7

List ename, job, annual salary, deptno, dname and grade who earn 30000 per year and who are not clerks.

### Procedure

* **DQL Command:** Use AND condition.

### Query

```sql
SELECT e.ename,
       e.job,
       e.sal*12 AS annual_salary,
       e.deptno,
       d.dname,
       s.grade
FROM employee e
JOIN department d ON e.deptno = d.deptno
JOIN salgrade s ON e.sal BETWEEN s.losal AND s.hisal
WHERE e.sal*12 = 30000
  AND e.job <> 'CLERK';
```

### Output

| ename | job     | annual_salary | deptno | dname | grade |
| ----- | ------- | ------------- | ------ | ----- | ----- |
| BLAKE | MANAGER | 30000         | 30     | SALES | 4     |

---

## Question 8

List employees with their manager name and number. Display 'No Manager' if none.

### Procedure

* **DQL Command:** Use SELF JOIN + IFNULL().

### Query

```sql
SELECT e.empno,
       e.ename,
       IFNULL(m.empno,'No Manager') AS mgr_no,
       IFNULL(m.ename,'No Manager') AS mgr_name
FROM employee e
LEFT JOIN employee m
ON e.mgr = m.empno;
```

### Output

| empno | ename | mgr_no     | mgr_name   |
| ----- | ----- | ---------- | ---------- |
| 7839  | KING  | No Manager | No Manager |

---

## Question 9

Select dept name, dept no and sum of salary.

### Procedure

* **DQL Command:** Use SUM() with GROUP BY.

### Query

```sql
SELECT d.dname,
       d.deptno,
       SUM(e.sal) AS total_salary
FROM employee e
JOIN department d
ON e.deptno = d.deptno
GROUP BY d.deptno, d.dname;
```

### Output

| dname | deptno | total_salary |
| ----- | ------ | ------------ |
| SALES | 30     | 9400         |

---

## Question 10

Display employee number, name and department location.

### Procedure

* **DQL Command:** Use JOIN.

### Query

```sql
SELECT e.empno,
       e.ename,
       d.loc
FROM employee e
JOIN department d
ON e.deptno = d.deptno;
```

### Output

| empno | ename | loc    |
| ----- | ----- | ------ |
| 7369  | SMITH | DALLAS |

---

## Question 11

Display employee name and department name for each employee.

### Procedure

* **DQL Command:** Use INNER JOIN.

### Query

```sql
SELECT e.ename,
       d.dname
FROM employee e
JOIN department d
ON e.deptno = d.deptno;
```

### Output

| ename | dname |
| ----- | ----- |
| ALLEN | SALES |

---

<p align="center">✨✅ <b>Experiment 8 Successfully Completed</b> ✅✨</p>
```
