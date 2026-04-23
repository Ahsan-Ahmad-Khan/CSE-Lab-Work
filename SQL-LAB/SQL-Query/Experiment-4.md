Perfect Ahsan ✨
Here is **Experiment 4** rewritten exactly like Experiment 5 —

✔ Proper Markdown structure
✔ Aim → Procedure (with Command Type specified) → Query → Output
✔ DQL / DML clearly mentioned
✔ Clean GitHub-ready format

You can directly paste this into `Experiment-4.md` 👇

---

````markdown
# SQL Lab – Experiment 4

## Aim
To practice conditional queries, pattern matching, calculations, ordering and update operations on employee table.

---

## Question 1
Display the list of employees who have joined the company before 30th June 1980 or after 31st Dec 1981.

### Procedure
- **DQL Command:** Use `WHERE` clause with date conditions.
- `OR` operator is used to combine multiple conditions.

### Query
```sql
SELECT ename, hiredate 
FROM employee 
WHERE hiredate < '1980-06-30' 
   OR hiredate > '1981-12-31';
````

### Output

| ename | hiredate   |
| ----- | ---------- |
| SMITH | 1980-05-01 |
| SCOTT | 1982-12-09 |

---

## Question 2

Display the names of employees whose names have second alphabet A.

### Procedure

* **DQL Command:** Use `LIKE` operator for pattern matching.
* `_` represents a single character.
* `%` represents multiple characters.

### Query

```sql
SELECT ename 
FROM employee 
WHERE ename LIKE '_A%';
```

### Output

| ename |
| ----- |
| JAMES |
| BLAKE |

---

## Question 3

Display the names of employees whose name is exactly five characters in length.

### Procedure

* **DQL Command:** Use `LIKE` with five underscores (`_____`).
* Each `_` represents one character.

### Query

```sql
SELECT ename 
FROM employee 
WHERE ename LIKE '_____';
```

### Output

| ename |
| ----- |
| SMITH |
| ALLEN |
| JONES |

---

## Question 4

Display the names of employees whose names have second alphabet A.

### Procedure

* **DQL Command:** Use `LIKE` operator with `_A%` pattern.



### Query

```sql
SELECT ename 
FROM employee 
WHERE ename LIKE '_A%';
```

### Output

| ename |
| ----- |
| JAMES |
| BLAKE |

---

## Question 5

Display the names of employees who are not working as salesman or clerk or analyst.

### Procedure

* **DQL Command:** Use `NOT IN` to exclude specific job roles.

### Query

```sql
SELECT ename 
FROM employee 
WHERE job NOT IN ('SALESMAN','CLERK','ANALYST');
```

### Output

| ename |
| ----- |
| KING  |
| BLAKE |

---

## Question 6

Display the name of the employee along with their annual salary (sal*12). The name of the employee earning highest salary should appear first.

### Procedure

* **DQL Command:** Use arithmetic expression `sal*12`.
* `ORDER BY` is used to sort results in descending order.

### Query

```sql
SELECT ename, sal*12 AS annual_salary 
FROM employee 
ORDER BY sal DESC;
```

### Output

| ename | annual_salary |
| ----- | ------------- |
| KING  | 60000         |
| SCOTT | 36000         |

---

## Question 7

Display name, sal, hra, pf, da, totalsal for each employee.

* HRA = 15% of sal
* DA = 10% of sal
* PF = 5% of sal
* Total Salary = (sal + hra + da) - pf

### Procedure

* **DQL Command:** Use arithmetic expressions for calculations.
* `ORDER BY` used to sort by total salary.

### Query

```sql
SELECT ename, sal, 
       sal*0.15 AS hra, 
       sal*0.10 AS da, 
       sal*0.05 AS pf, 
       (sal+(sal*0.15)+(sal*0.10))-(sal*0.05) AS totalsal 
FROM employee 
ORDER BY totalsal;
```

### Output

| ename | sal  | hra | da  | pf  | totalsal |
| ----- | ---- | --- | --- | --- | -------- |
| SMITH | 800  | 120 | 80  | 40  | 960      |
| KING  | 5000 | 750 | 500 | 250 | 6000     |

---

## Question 8

Update the salary of each employee by 10% increment who are not eligible for commission.

### Procedure

* **DML Command:** Use `UPDATE` to modify existing records.
* `SET` is used to change salary.
* `WHERE` ensures only specific records are updated.

### Query

```sql
UPDATE employee 
SET sal = sal*1.10 
WHERE comm IS NULL;
```

### Output

| Rows Affected |
| ------------- |
| 4             |

---

## Question 9

Display those employees whose salary is more than 3000 after giving 20% increment.

### Procedure

* **DQL Command:** Use arithmetic calculation in `WHERE` clause.

### Query

```sql
SELECT ename, sal*1.20 AS new_salary 
FROM employee 
WHERE sal*1.20 > 3000;
```

### Output

| ename | new_salary |
| ----- | ---------- |
| KING  | 6000       |
| SCOTT | 4320       |

---

## Question 10

Display those employees whose salary contains at least 3 digits.

### Procedure

* **DQL Command:** Use numeric comparison.
* Salary having at least 3 digits means salary ≥ 100.

### Query

```sql
SELECT ename, sal 
FROM employee 
WHERE sal >= 100;
```

### Output

| ename | sal  |
| ----- | ---- |
| SMITH | 800  |
| ALLEN | 1600 |
| KING  | 5000 |

---

<p align="center">✨✅ <b>Experiment 4 Successfully Completed</b> ✅✨</p>
```


---
