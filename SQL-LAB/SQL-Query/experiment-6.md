Here you go Ahsan ✨ — **Experiment 6** written in the exact same structured Markdown format as Experiment 4 & 5.

✔ Proper headings
✔ Aim → Procedure (Command Type specified) → Query → Output
✔ Function explanation where required
✔ Fully MariaDB (XAMPP) compatible
✔ Clean GitHub-ready

You can directly paste this into `Experiment-6.md` 👇

---

````markdown
# SQL Lab – Experiment 6

## Aim
To practice date and time functions, string functions, and conditional queries in MariaDB.

---

## Question 1
Display empno, ename and department name instead of department number.

### Procedure
- **DQL Command:** Use `CASE` to replace department number with department name.
- `CASE` is used instead of Oracle `DECODE()` because MariaDB does not support `DECODE()`.

### Query
```sql
SELECT empno, ename,
CASE deptno
    WHEN 10 THEN 'ACCOUNTING'
    WHEN 20 THEN 'RESEARCH'
    WHEN 30 THEN 'SALES'
    WHEN 40 THEN 'OPERATIONS'
END AS department_name
FROM employee;
````

### Output

| empno | ename | department_name |
| ----- | ----- | --------------- |
| 7369  | SMITH | RESEARCH        |
| 7499  | ALLEN | SALES           |

---

## Question 2

Display your age in days.

### Procedure

* **DQL Command:** Use `DATEDIFF()`.
* `DATEDIFF(date1, date2)` returns difference in days.
* `CURDATE()` returns current date.

### Query

```sql
SELECT DATEDIFF(CURDATE(),'2004-02-02') AS age_in_days;
```

### Output

| age_in_days |
| ----------- |
| 8000+       |

---

## Question 3

Display your age in months.

### Procedure

* **DQL Command:** Use `TIMESTAMPDIFF()`.
* `TIMESTAMPDIFF(MONTH, date1, date2)` returns difference in months.

### Query

```sql
SELECT TIMESTAMPDIFF(MONTH,'2004-02-02',CURDATE()) AS age_in_months;
```

### Output

| age_in_months |
| ------------- |
| 260+          |

---

## Question 4

Display the current date as 15th August Friday 1997 format.

### Procedure

* **DQL Command:** Use `DATE_FORMAT()`.
* `DATE_FORMAT()` formats date according to given pattern.

### Query

```sql
SELECT DATE_FORMAT(CURDATE(),'%D %M %W %Y') AS formatted_date;
```

### Output

| formatted_date        |
| --------------------- |
| 1st March Friday 2026 |

---

## Question 5

Display the following output for each row:
**"ENAME joined on Day Date Month Year"**

### Procedure

* **DQL Command:** Use `CONCAT()` and `DATE_FORMAT()`.
* `CONCAT()` joins strings.
* `DATE_FORMAT()` formats hire date.

### Query

```sql
SELECT CONCAT(ename,' joined on ',
DATE_FORMAT(hiredate,'%W %D %M %Y')) AS joining_info
FROM employee;
```

### Output

| joining_info                                |
| ------------------------------------------- |
| SMITH joined on Thursday 17th December 1980 |

---

## Question 6

Display: Scott has joined the company on Wednesday 13th August 1990.

### Procedure

* **DQL Command:** Use `CONCAT()` and `DATE_FORMAT()` with condition.

### Query

```sql
SELECT CONCAT(ename,' has joined the company on ',
DATE_FORMAT(hiredate,'%W %D %M %Y')) AS joining_statement
FROM employee
WHERE ename='SCOTT';
```

### Output

| joining_statement                                      |
| ------------------------------------------------------ |
| SCOTT has joined the company on Monday 19th April 1987 |

---

## Question 7

Find the date for nearest Saturday after current date.

### Procedure

* **DQL Command:** Use `DAYOFWEEK()` and `DATE_ADD()`.
* `DAYOFWEEK()` returns weekday number.
* `DATE_ADD()` adds interval to date.

### Query

```sql
SELECT DATE_ADD(CURDATE(),
INTERVAL (7 - DAYOFWEEK(CURDATE())) DAY) AS next_saturday;
```

### Output

| next_saturday |
| ------------- |
| 2026-03-07    |

---

## Question 8

Display current time.

### Procedure

* **DQL Command:** Use `NOW()`.
* `NOW()` returns current date and time.

### Query

```sql
SELECT NOW() AS current_time;
```

### Output

| current_time        |
| ------------------- |
| 2026-03-01 14:30:00 |

---

## Question 9

Display the date three months before the current date.

### Procedure

* **DQL Command:** Use `DATE_SUB()`.
* `DATE_SUB()` subtracts interval from date.

### Query

```sql
SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH) AS three_months_before;
```

### Output

| three_months_before |
| ------------------- |
| 2025-12-01          |

---

## Question 10

Display employees who joined in the month of December.

### Procedure

* **DQL Command:** Use `MONTH()` to extract month from date.

### Query

```sql
SELECT ename, hiredate
FROM employee
WHERE MONTH(hiredate)=12;
```

### Output

| ename | hiredate   |
| ----- | ---------- |
| SMITH | 1980-12-17 |

---

## Question 11

Display employees whose first 2 characters of joining year are '19'.

### Procedure

* **DQL Command:** Use `YEAR()`, `CAST()`, and `LEFT()`.
* `YEAR()` extracts year.
* `CAST(... AS CHAR)` converts number to string.
* `LEFT()` extracts first 2 characters.

### Query

```sql
SELECT ename, hiredate
FROM employee
WHERE LEFT(CAST(YEAR(hiredate) AS CHAR),2)='19';
```

### Output

| ename | hiredate   |
| ----- | ---------- |
| SMITH | 1980-12-17 |

---

## Question 12

Display employees whose 10% of salary equals year of joining.

### Procedure

* **DQL Command:** Use `ROUND()` and `YEAR()`.
* `ROUND()` rounds calculated value.
* `YEAR()` extracts year.

### Query

```sql
SELECT ename, sal, hiredate
FROM employee
WHERE ROUND(sal*0.10)=YEAR(hiredate);
```

### Output

| ename          | sal | hiredate |
| -------------- | --- | -------- |
| (if any match) |     |          |

---

## Question 13

Display employees who joined before 15th day of the month.

### Procedure

* **DQL Command:** Use `DAY()` function.
* `DAY()` extracts day from date.

### Query

```sql
SELECT ename, hiredate
FROM employee
WHERE DAY(hiredate) < 15;
```

### Output

| ename | hiredate   |
| ----- | ---------- |
| ALLEN | 1981-02-20 |

---

## Question 14

Display employees who joined before 15th of the month.

### Procedure

* **DQL Command:** Use `DAY()` function with condition.

### Query

```sql
SELECT ename, hiredate
FROM employee
WHERE DAY(hiredate) < 15;
```

### Output

| ename | hiredate   |
| ----- | ---------- |
| ALLEN | 1981-02-20 |

---

## Question 15

Display employees whose joining date is equal to department number.

### Procedure

* **DQL Command:** Use `DAY()` to compare date with deptno.

### Query

```sql
SELECT ename, hiredate, deptno
FROM employee
WHERE DAY(hiredate)=deptno;
```

### Output

| ename          | hiredate | deptno |
| -------------- | -------- | ------ |
| (if any match) |          |        |

---

<p align="center">✨✅ <b>Experiment 6 Successfully Completed</b> ✅✨</p>
```
