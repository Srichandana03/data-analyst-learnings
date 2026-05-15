# 🚀 SQL Day 4 Notes | NULL Handling, Filtering Operators & Interview Questions

---

# 📌 Day 4 Overview

Today I focused on understanding how SQL handles NULL values, filtering data using different operators, and solving interview-oriented SQL questions.

I also practiced real-world query scenarios, revised SQL execution flow, and solved a HackerRank SQL problem.

---

# 📚 Concepts Learned Today

- NULL in SQL
- IS NULL & IS NOT NULL
- IFNULL()
- COALESCE()
- NULLIF()
- Difference between IFNULL(), COALESCE(), and NULLIF()
- AND / OR / NOT
- IN Operator
- BETWEEN Operator
- LIKE Operator
- DISTINCT
- COUNT()
- COUNT(DISTINCT)
- WHERE vs HAVING
- SQL Execution Order
- DISTINCT performance implications

---

# 📌 NULL in SQL

`NULL` represents:
- missing value
- unknown value
- undefined data

Important:

```sql
NULL ≠ 0
NULL ≠ ''
```

NULL behaves differently from normal values.

---

# 📌 IS NULL

Used to check NULL values.

## ✅ Syntax

```sql
SELECT column_name
FROM table_name
WHERE column_name IS NULL;
```

## ✅ Example

```sql
SELECT *
FROM employees
WHERE manager_id IS NULL;
```

Shows employees without managers.

---

# 📌 IS NOT NULL

Used to find non-null values.

## ✅ Syntax

```sql
SELECT column_name
FROM table_name
WHERE column_name IS NOT NULL;
```

## ✅ Example

```sql
SELECT *
FROM employees
WHERE salary IS NOT NULL;
```

---

# 📌 IFNULL()

`IFNULL()` replaces NULL with another value.

## ✅ Syntax

```sql
IFNULL(value,replacement)
```

## ✅ Example

```sql
SELECT employee_name,
IFNULL(phone,'No Number') AS contact
FROM employees;
```

If phone is NULL:
```sql
No Number
```

will be displayed.

---

# 📌 COALESCE()

`COALESCE()` returns the first non-null value.

## ✅ Syntax

```sql
COALESCE(value1,value2,value3...)
```

## ✅ Example

```sql
SELECT employee_name,
COALESCE(phone,email,'No Contact') AS contact
FROM employees;
```

Priority:
- phone
- else email
- else No Contact

---

# 📌 NULLIF()

`NULLIF()` returns NULL if two values are equal.

## ✅ Syntax

```sql
NULLIF(value1,value2)
```

## ✅ Example

```sql
SELECT NULLIF(100,100);
```

Returns:
```sql
NULL
```

---

# 📌 Real-world Use of NULLIF()

Used to avoid divide-by-zero errors.

---

## ❌ Problem Query

```sql
SELECT marks / total_marks
FROM students;
```

If:
```sql
total_marks = 0
```

SQL throws:
```sql
Divide by zero error
```

---

## ✅ Solution Using NULLIF()

```sql
SELECT marks / NULLIF(total_marks,0)
FROM students;
```

If total_marks becomes 0:

```sql
NULLIF(0,0)
```

returns:

```sql
NULL
```

So query becomes:

```sql
marks / NULL
```

which safely returns NULL instead of an error.

---

# 📌 Difference Between IFNULL(), COALESCE(), and NULLIF()

| Feature | IFNULL() | COALESCE() | NULLIF() |
|---|---|---|---|
| Purpose | Replaces NULL | Returns first non-null value | Creates NULL if values are equal |
| Syntax | `IFNULL(a,b)` | `COALESCE(a,b,c)` | `NULLIF(a,b)` |
| Arguments | Only 2 | Multiple | Only 2 |
| Main Use | Simple NULL replacement | Multiple fallback values | Avoid divide-by-zero |
| ANSI Standard SQL | No | Yes | Yes |
| Flexibility | Less | High | Medium |
| Real-world Use | Reports/Dashboards | Production SQL | Error handling |
| Output Logic | NULL → replacement | first non-null | equal → NULL |

---

# 📌 AND / OR / NOT

Logical operators used in filtering data.

---

## ✅ AND

Both conditions must be true.

```sql
SELECT *
FROM students
WHERE marks > 80 AND city='Hyderabad';
```

---

## ✅ OR

Any one condition can be true.

```sql
SELECT *
FROM students
WHERE city='Delhi' OR city='Mumbai';
```

---

## ✅ NOT

Reverses condition.

```sql
SELECT *
FROM students
WHERE NOT city='Delhi';
```

---

# 📌 IN Operator

Used for checking multiple values.

## ✅ Example

```sql
SELECT *
FROM students
WHERE city IN ('Delhi','Mumbai','Hyderabad');
```

---

# 📌 BETWEEN Operator

Used for ranges.

## ✅ Example

```sql
SELECT *
FROM products
WHERE price BETWEEN 100 AND 500;
```

---

# 📌 LIKE Operator

Used for pattern matching.

---

## ✅ Starts with A

```sql
WHERE name LIKE 'A%'
```

---

## ✅ Ends with a

```sql
WHERE name LIKE '%a'
```

---

## ✅ Contains "an"

```sql
WHERE name LIKE '%an%'
```

---

# 📌 DISTINCT

`DISTINCT` removes duplicate values.

## ✅ Example

```sql
SELECT DISTINCT city
FROM employees;
```

Shows only unique city names.

---

# 📌 DISTINCT Performance Learning

Learned that `DISTINCT` internally may use:
- sorting
- hashing

This can:
- increase memory usage
- slow queries on huge datasets
- increase CPU usage

---

# 📌 COUNT()

Used to count rows/values.

---

## ✅ COUNT(*)

Counts all rows.

```sql
SELECT COUNT(*)
FROM employees;
```

---

## ✅ COUNT(column)

Counts non-null values.

```sql
SELECT COUNT(phone)
FROM employees;
```

---

## ✅ COUNT(DISTINCT column)

Counts unique non-null values.

```sql
SELECT COUNT(DISTINCT city)
FROM employees;
```

---

# 📌 WHERE vs HAVING

| WHERE | HAVING |
|---|---|
| Filters rows | Filters grouped data |
| Used before GROUP BY | Used after GROUP BY |
| Cannot directly use aggregates | Works with aggregate functions |

---

# 📌 SQL Execution Order

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

# 🧠 Interview Questions Practiced

Practiced questions on:
- WHERE vs HAVING
- DISTINCT performance implications
- SQL execution order
- NULL handling functions
- SELECT * on huge tables
- COUNT vs COUNT(DISTINCT)

---

# 🏆 HackerRank SQL Problem Solved

## Problem

Find difference between total CITY entries and distinct CITY entries.

## Concepts Used

- COUNT()
- COUNT(DISTINCT)
- DISTINCT

## ✅ Query

```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
FROM STATION;
```

---

# 💡 Important Learning Today

Today I understood:
- how SQL handles missing data
- practical use of NULL functions
- real-world use of NULLIF()
- performance implications of DISTINCT
- difference between counting rows and unique values
- interview-oriented SQL concepts
- importance of query optimization

---

# 🎯 Day 4 Summary

Today I:
- Learned NULL handling in SQL
- Practiced IFNULL(), COALESCE(), NULLIF()
- Learned AND, OR, NOT, IN, BETWEEN, LIKE
- Revised WHERE vs HAVING
- Learned COUNT() and COUNT(DISTINCT)
- Understood DISTINCT performance implications
- Practiced SQL interview questions
- Solved 1 HackerRank problem
- Improved SQL query writing and logical thinking

---