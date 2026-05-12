📌 What is SQL?

SQL stands for Structured Query Language.

It is used to communicate with databases.

Using SQL, we can:

📥 Retrieve data
📤 Insert data
✏️ Update data
❌ Delete data
🔍 Filter data
📊 Analyze data
🗄️ What is a Relational Database?

A Relational Database stores data in the form of tables.

Each table contains:

Rows → Records
Columns → Attributes
📖 Example Table
id	name	department
1	Ram	IT
2	Ravi	HR
🔹 SELECT Statement

SELECT is used to retrieve data from a table.

✅ Syntax
SELECT column_name
FROM table_name;
✅ Example
SELECT name
FROM employees;

This retrieves only the name column.

🔹 SELECT *

* means all columns.

✅ Example
SELECT *
FROM employees;

This retrieves the complete table.

🔹 SELECT DISTINCT

DISTINCT removes duplicate values.

✅ Syntax
SELECT DISTINCT column_name
FROM table_name;
✅ Example
SELECT DISTINCT department
FROM employees;

If multiple employees belong to IT, IT will be shown only once.

🔍 WHERE Clause

WHERE is used to filter rows.

✅ Syntax
SELECT *
FROM employees
WHERE condition;
✅ Example
SELECT *
FROM employees
WHERE department = 'IT';

This retrieves employees from the IT department.

⚡ Relational Operators in WHERE
Operator	Meaning
=	Equal to
!= or <>	Not equal to
>	Greater than
<	Less than
>=	Greater than or equal to
<=	Less than or equal to
✅ Examples
SELECT *
FROM employees
WHERE salary > 50000;
SELECT *
FROM employees
WHERE age <= 25;
🔗 Logical Operators
✅ AND Operator

Both conditions must be true.

SELECT *
FROM employees
WHERE department = 'IT' AND salary > 50000;
✅ OR Operator

At least one condition must be true.

SELECT *
FROM employees
WHERE department = 'IT' OR department = 'HR';
🎯 LIKE Operator

LIKE is used for pattern matching.

🔹 % Wildcard

% represents multiple characters.

✅ Example
SELECT *
FROM employees
WHERE name LIKE 'R%';
📌 Output:

Names starting with R

Examples:

Ram
Ravi
✅ Example
SELECT *
FROM employees
WHERE name LIKE '%a';
📌 Output:

Names ending with a

🔹 _ Wildcard

_ represents exactly one character.

✅ Example
SELECT *
FROM employees
WHERE name LIKE '_a%';

Second character must be a.

📊 ORDER BY

ORDER BY is used to sort data.

🔹 Ascending Order
SELECT *
FROM employees
ORDER BY salary ASC;
🔹 Descending Order
SELECT *
FROM employees
ORDER BY salary DESC;
🧩 GROUP BY

GROUP BY groups rows having the same values.

It is mostly used with aggregate functions.

✅ Example
SELECT department
FROM employees
GROUP BY department;

This groups employees department-wise.

📈 Aggregate Functions

Aggregate functions perform calculations on multiple rows and return a single value.

Function	Purpose
COUNT()	Counts rows
SUM()	Adds values
AVG()	Finds average
MAX()	Finds maximum value
MIN()	Finds minimum value
🔹 COUNT()
SELECT COUNT(*)
FROM employees;

Counts total rows.

🔹 SUM()
SELECT SUM(salary)
FROM employees;

Adds all salary values.

🔹 AVG()
SELECT AVG(salary)
FROM employees;

Finds average salary.

🔹 MAX()
SELECT MAX(salary)
FROM employees;

Finds highest salary.

🔹 MIN()
SELECT MIN(salary)
FROM employees;

Finds lowest salary.

📌 GROUP BY with Aggregate Functions
✅ Example
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
📖 Output
department	COUNT(*)
IT	2
HR	1
✅ Explanation
Rows are grouped by department
COUNT(*) counts employees in each department
🚨 HAVING Clause

HAVING is used to filter grouped data.

📌 Important Difference
WHERE	HAVING
Filters rows	Filters groups
Executes before GROUP BY	Executes after GROUP BY
Cannot use aggregate functions	Can use aggregate functions
❌ Wrong Query
SELECT department, COUNT(*)
FROM employees
WHERE COUNT(*) > 1
GROUP BY department;
🚨 Why Error?

Because:

WHERE executes before grouping
COUNT() is calculated after grouping
✅ Correct Query Using HAVING
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 1;

This retrieves departments having more than 1 employee.

⚙️ SQL Execution Order
FROM
WHERE
GROUP BY
HAVING
SELECT
ORDER BY
LIMIT

Understanding execution order is very important in SQL.

🔢 LIMIT Clause

LIMIT restricts the number of rows returned.

✅ Example
SELECT *
FROM employees
LIMIT 3;

Returns first 3 rows.

🔹 LIMIT with Offset
SELECT *
FROM employees
LIMIT 2, 1;
📌 Meaning
Start from index 2
Return 1 row

Useful for pagination.

🏷️ Aliasing

Aliasing gives temporary names to columns or tables.

🔹 Column Alias
SELECT salary AS employee_salary
FROM employees;

Here:

employee_salary is an alias
🔹 Table Alias
SELECT e.name
FROM employees AS e;

e becomes a short name for the table.

🎯 Day 1 Summary

Today I learned:

✅ SQL Basics
✅ Relational Databases
✅ SELECT & DISTINCT
✅ WHERE Clause
✅ Relational & Logical Operators
✅ LIKE Operator (% and _)
✅ ORDER BY
✅ GROUP BY
✅ Aggregate Functions
✅ HAVING Clause
✅ LIMIT
✅ Aliasing

🚀 Final Note

SQL is one of the most important skills for:

📊 Data Analytics
🤖 Data Science
🧠 Machine Learning
🌐 Backend Development

Strong SQL fundamentals help in analyzing and managing data efficiently.

🔥 Day 1 Completed Successfully