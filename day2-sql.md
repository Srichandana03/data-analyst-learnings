🚀 SQL Day 2 Notes | Hands-on Practice & Database Commands
📌 Day 2 Overview

Today I:

Revised all concepts learned on Day 1
Gained hands-on SQL practice
Solved 7 HackerRank SQL problems
Learned SQL command categories
Practiced table creation and modification commands
🗄️ Relational Databases

A Relational Database stores data in the form of related tables.

Each table contains:

📌 Rows → Records
📌 Columns → Attributes

Tables are connected using:

Primary Keys
Foreign Keys
📖 Example Table
customer_id	name	city
1	Chinnu	UK
2	Kru	Mumbai
⚡ SQL Command Categories

SQL commands are divided into different categories.

Category	Full Form	Purpose
DDL	Data Definition Language	Defines database structure
DML	Data Manipulation Language	Manipulates data
DQL	Data Query Language	Retrieves data
DCL	Data Control Language	Controls permissions
🔹 DDL (Data Definition Language)

DDL commands are used to define or modify database structure.

Commands include:

CREATE
ALTER
DROP
TRUNCATE
🏗️ CREATE Command

CREATE is used to create databases or tables.

✅ Create Database
CREATE DATABASE practice_db;
✅ Create Table
CREATE TABLE customers (
    customer_id INT,
    name VARCHAR(50),
    city VARCHAR(50)
);
✏️ ALTER Command

ALTER is used to modify table structure.

We can:

add columns
remove columns
change datatype
rename columns
✅ Add Column
ALTER TABLE customers
ADD phone VARCHAR(15);
✅ Modify Datatype
ALTER TABLE customers
MODIFY phone BIGINT;
✅ Drop Column
ALTER TABLE customers
DROP COLUMN phone;
❌ DROP Command

DROP completely deletes the table.

Both:

structure
data

will be removed permanently.

✅ Example
DROP TABLE customers;

After this:

table no longer exists
🧹 TRUNCATE Command

TRUNCATE removes all rows from the table but keeps the table structure.

✅ Example
TRUNCATE TABLE customers;

After truncate:

columns remain
table exists
only data is deleted
📌 Difference Between DROP and TRUNCATE
TRUNCATE	DROP
Deletes rows only	Deletes entire table
Structure remains	Structure removed
Table still exists	Table deleted completely
🔹 DML (Data Manipulation Language)

DML commands are used to manipulate data inside tables.

Commands include:

INSERT
UPDATE
DELETE
📥 INSERT Command

INSERT is used to add data into tables.

✅ Insert Single Row
INSERT INTO customers
VALUES (1, 'Chandu', 'Bangalore');
✅ Insert Multiple Rows
INSERT INTO customers
VALUES
(1, 'Chinnu', 'UK'),
(2, 'Kru', 'Mumbai'),
(3, 'Chandu', 'Bangalore');
🔄 UPDATE Command

UPDATE modifies existing data.

✅ Example
UPDATE customers
SET city = 'Hyderabad'
WHERE customer_id = 1;
❌ DELETE Command

DELETE removes rows from a table.

✅ Example
DELETE FROM customers
WHERE customer_id = 2;

Only matching rows are deleted.

🔍 DQL (Data Query Language)

DQL is used to retrieve data.

Main command:

SELECT
✅ Example
SELECT *
FROM customers;

Retrieves complete table data.

🔐 DCL (Data Control Language)

DCL commands control user permissions.

Commands include:

GRANT
REVOKE
✅ GRANT Example
GRANT SELECT ON customers TO user1;

Gives SELECT permission.

✅ REVOKE Example
REVOKE SELECT ON customers FROM user1;

Removes permission.

📌 Difference Between ALTER and UPDATE
ALTER	UPDATE
Changes table structure	Changes data
Works on columns	Works on row values
✅ ALTER Example
ALTER TABLE customers
ADD email VARCHAR(50);
✅ UPDATE Example
UPDATE customers
SET city = 'Chennai'
WHERE customer_id = 2;
📌 Difference Between DELETE, TRUNCATE and DROP
Command	Deletes Rows	Deletes Structure
DELETE	✅ Yes	❌ No
TRUNCATE	✅ All Rows	❌ No
DROP	✅ Yes	✅ Yes
🧠 Important Learnings
📌 VARCHAR vs INT for Phone Numbers

Phone numbers are usually stored as:

VARCHAR

because:

phone numbers are not used for calculations
leading zeros should be preserved
country codes like +91 may be used
📌 SQL Execution Flow Learned
FROM
WHERE
GROUP BY
HAVING
SELECT
ORDER BY
LIMIT
🎯 Day 2 Summary

Today I:

Revised SQL basics
Practiced commands hands-on
Solved 7 HackerRank SQL problems
Learned SQL command categories
Understood CREATE, ALTER, DROP, TRUNCATE
Practiced INSERT, UPDATE and DELETE
Learned difference between ALTER and UPDATE
Learned difference between DELETE, TRUNCATE and DROP
