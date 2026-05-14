# 🚀 SQL Day 3 Notes | Aggregate Functions & Query Practice

---

# 📌 Day 3 Overview

Today I:

- Learned Aggregate Functions
- Practiced GROUP BY queries
- Learned ORDER BY sorting
- Understood HAVING clause
- Learned LIMIT and DISTINCT
- Practiced Aliasing
- Solved 1 HackerRank SQL problem
- Gained hands-on query writing practice

---

# 🔢 Aggregate Functions

Aggregate functions perform calculations on multiple rows and return a single value.

## Functions Learned:
- COUNT()
- SUM()
- AVG()
- MAX()
- MIN()

---

# 📌 COUNT()

`COUNT()` is used to count rows.

## ✅ Example

```sql
SELECT COUNT(*) 
FROM employees;
```

Counts total employees.

---

# 📌 AVG()

`AVG()` returns the average value.

## ✅ Example

```sql
SELECT AVG(salary)
FROM employees;
```

Finds average salary.

---

# 📌 MAX()

`MAX()` returns the highest value.

## ✅ Example

```sql
SELECT MAX(salary)
FROM employees;
```

Finds highest salary.

---

# 📌 MIN()

`MIN()` returns the lowest value.

## ✅ Example

```sql
SELECT MIN(salary)
FROM employees;
```

Finds lowest salary.

---

# 📌 SUM()

`SUM()` adds all values.

## ✅ Example

```sql
SELECT SUM(salary)
FROM employees;
```

Calculates total salary.

---

# 📂 GROUP BY

`GROUP BY` is used to group rows having the same values.

Mostly used with aggregate functions.

## ✅ Example

```sql
SELECT city, COUNT(emp_id)
FROM employees
GROUP BY city;
```

Counts employees city-wise.

---

# 📊 ORDER BY

`ORDER BY` is used to sort data.

## ✅ Descending Order

```sql
SELECT *
FROM employees
ORDER BY salary DESC;
```

Shows highest salary first.

---

## ✅ Ascending Order

```sql
SELECT *
FROM employees
ORDER BY salary ASC;
```

Shows lowest salary first.

---

# 📌 HAVING Clause

`HAVING` is used to filter grouped data.

## ✅ Example

```sql
SELECT city, COUNT(emp_id)
FROM employees
GROUP BY city
HAVING COUNT(emp_id) > 1;
```

Shows cities having more than 1 employee.

---

# 📌 WHERE vs HAVING

| WHERE | HAVING |
|-------|--------|
| Filters rows | Filters grouped data |
| Used before GROUP BY | Used after GROUP BY |
| Works on normal rows | Works on aggregate results |

---

# 📌 LIMIT

`LIMIT` restricts the number of rows returned.

## ✅ Example

```sql
SELECT *
FROM employees
LIMIT 3;
```

Displays only 3 rows.

---

# 📌 DISTINCT

`DISTINCT` removes duplicate values.

## ✅ Example

```sql
SELECT DISTINCT city
FROM employees;
```

Shows unique city names.

---

# 📌 Aliasing

Aliasing gives temporary names to columns or tables.

## ✅ Example

```sql
SELECT AVG(salary) AS average_salary
FROM employees;
```

Here:
- `average_salary` is an alias name

---

# 📌 Important Learning

Aliasing is:
- not mandatory
- mainly used for readability
- commonly used with aggregate functions

---

# 🧠 Hands-on Practice

Practiced:
- Sorting salaries
- Grouping cities
- Counting employees
- Removing duplicates
- Writing aggregate queries
- Filtering grouped data

---

# 💡 Realization During Practice

While grouping cities, I found that:

```sql
Bangalore
```

and

```sql
Banglore
```

were treated as different values because of spelling difference.

This helped me understand:
- Data consistency
- Typo issues in databases
- Real-world data cleaning importance

---

# 🏆 HackerRank SQL Problem Solved

## Problem:
Query CITY names with even ID numbers and remove duplicates.

## Concepts Used:
- DISTINCT
- WHERE
- MOD()

## Key Learning:
Some SQL databases use:

```sql
MOD(ID,2)
```

instead of:

```sql
ID % 2
```

for checking even numbers.

---

# 📌 SQL Execution Flow Revised

```sql
FROM
WHERE
GROUP BY
HAVING
SELECT
ORDER BY
LIMIT
```

---

# 🎯 Day 3 Summary

Today I:

- Learned aggregate functions
- Practiced GROUP BY and HAVING
- Learned ORDER BY sorting
- Understood LIMIT and DISTINCT
- Learned aliasing
- Practiced real SQL queries
- Solved a HackerRank SQL problem
- Improved hands-on SQL understanding

---