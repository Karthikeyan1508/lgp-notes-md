# SQL JOIN

- SQL joins are used to query data from two or more tables, based on a relationship between certain columns in these tables.
- The `JOIN` keyword is used in an SQL statement to query data from two or more tables, based on relationships.
- Tables in a database are often related to each other with keys.
- A **primary key** is a column (or combination of columns) with a unique value for each row.  
  This binds data together across tables without repeating all data in every table.

---

## Example Tables

### Persons Table

| P_Id | LastName  | FirstName | Address       | City      |
|------|-----------|-----------|----------------|-----------|
| 1    | Hansen    | Ola       | Timoteivn 10   | Sandnes   |
| 2    | Svendson  | Tove      | Borgvn 23      | Sandnes   |
| 3    | Pettersen | Kari      | Storgt 20      | Stavanger |

- `P_Id` is the primary key n the `Persons` table. This means that no two rows can
have the same `P_Id`. The `P_Id` distinguishes two persons even if they have the same name.

### Orders Table

| O_Id | OrderNo | P_Id |
|------|---------|------|
| 1    | 77895   | 3    |
| 2    | 44678   | 3    |
| 3    | 22456   | 1    |
| 4    | 24562   | 1    |
| 5    | 34764   | 15   |

- Note that the `O_Id` column is the primary key in the `Orders` table and that the `P_Id` column refers to
the persons in the `Persons` table without using their names.
Notice that the relationship between the two tables above is the `P_Id` column.

---

## Types of SQL JOINs

| JOIN Type     | Description |
|---------------|-------------|
| `JOIN` / `INNER JOIN` | Returns rows with at least one match in both tables |
| `LEFT JOIN`   | Returns all rows from the left table, even if no match in the right |
| `RIGHT JOIN`  | Returns all rows from the right table, even if no match in the left |
| `FULL JOIN`   | Returns rows with a match in either left or right table |

---

## SQL INNER JOIN

- Returns rows with at least one match in both tables.

### Syntax

```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

> `INNER JOIN` is the same as `JOIN`.

### SQL INNER JOIN Example

**The "Persons" table:**

| P_Id | LastName  | FirstName | Address        | City      |
|------|-----------|-----------|----------------|-----------|
| 1    | Hansen    | Ola       | Timoteivn 10   | Sandnes   |
| 2    | Svendson  | Tove      | Borgvn 23      | Sandnes   |
| 3    | Pettersen | Kari      | Storgt 20      | Stavanger |

**The "Orders" table:**

| O_Id | OrderNo | P_Id |
|------|---------|------|
| 1    | 77895   | 3    |
| 2    | 44678   | 3    |
| 3    | 22456   | 1    |
| 4    | 24562   | 1    |
| 5    | 34764   | 15   |


```sql
SELECT Persons.LastName, Persons.FirstName, Orders.OrderNo
FROM Persons
INNER JOIN Orders ON Persons.P_Id = Orders.P_Id
ORDER BY Persons.LastName;
```

#### Result

| LastName  | FirstName | OrderNo |
|-----------|-----------|---------|
| Hansen    | Ola       | 22456   |
| Hansen    | Ola       | 24562   |
| Pettersen | Kari      | 77895   |
| Pettersen | Kari      | 44678   |

- The INNER JOIN keyword return rows when there is at least one match in both tables. If there are rows
in `Persons` that do not have matches in `Orders`, those rows will NOT be listed.
---

## SQL LEFT JOIN

- Returns all rows from the left table, even if there are no matches in the right table.

### Syntax

```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

### Example
### SQL LEFT JOIN Example

**The "Persons" table:**

| P_Id | LastName  | FirstName | Address       | City      |
|------|-----------|-----------|---------------|-----------|
| 1    | Hansen    | Ola       | Timoteivn 10  | Sandnes   |
| 2    | Svendson  | Tove      | Borgvn 23     | Sandnes   |
| 3    | Pettersen | Kari      | Storgt 20     | Stavanger |

**The "Orders" table:**

| O_Id | OrderNo | P_Id |
|------|---------|------|
| 1    | 77895   | 3    |
| 2    | 44678   | 3    |
| 3    | 22456   | 1    |
| 4    | 24562   | 1    |
| 5    | 34764   | 15   |


```sql
SELECT Persons.LastName, Persons.FirstName, Orders.OrderNo
FROM Persons
LEFT JOIN Orders ON Persons.P_Id = Orders.P_Id
ORDER BY Persons.LastName;
```

#### Result

| LastName  | FirstName | OrderNo |
|-----------|-----------|---------|
| Hansen    | Ola       | 22456   |
| Hansen    | Ola       | 24562   |
| Pettersen | Kari      | 77895   |
| Pettersen | Kari      | 44678   |
| Svendson  | Tove      | *null*  |

---

## SQL RIGHT JOIN

- Returns all rows from the right table, even if there are no matches in the left table.

### Syntax

```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

### Example

### SQL RIGHT JOIN Example

**The "Persons" table:**

| P_Id | LastName  | FirstName | Address       | City      |
|------|-----------|-----------|---------------|-----------|
| 1    | Hansen    | Ola       | Timoteivn 10  | Sandnes   |
| 2    | Svendson  | Tove      | Borgvn 23     | Sandnes   |
| 3    | Pettersen | Kari      | Storgt 20     | Stavanger |

**The "Orders" table:**

| O_Id | OrderNo | P_Id |
|------|---------|------|
| 1    | 77895   | 3    |
| 2    | 44678   | 3    |
| 3    | 22456   | 1    |
| 4    | 24562   | 1    |
| 5    | 34764   | 15   |


```sql
SELECT Persons.LastName, Persons.FirstName, Orders.OrderNo
FROM Persons
RIGHT JOIN Orders ON Persons.P_Id = Orders.P_Id
ORDER BY Persons.LastName;
```

#### Result

| LastName  | FirstName | OrderNo |
|-----------|-----------|---------|
| Hansen    | Ola       | 22456   |
| Hansen    | Ola       | 24562   |
| Pettersen | Kari      | 77895   |
| Pettersen | Kari      | 44678   |
| *null*    | *null*    | 34764   |

---

## SQL FULL JOIN

- Returns all rows from both tables. Rows without a match in one of the tables will have NULLs for the missing side.

### Syntax

```sql
SELECT column_name(s)
FROM table1
FULL JOIN table2
ON table1.column = table2.column;
```

### Example
### SQL FULL JOIN Example

**The "Persons" table:**

| P_Id | LastName  | FirstName | Address       | City      |
|------|-----------|-----------|---------------|-----------|
| 1    | Hansen    | Ola       | Timoteivn 10  | Sandnes   |
| 2    | Svendson  | Tove      | Borgvn 23     | Sandnes   |
| 3    | Pettersen | Kari      | Storgt 20     | Stavanger |

**The "Orders" table:**

| O_Id | OrderNo | P_Id |
|------|---------|------|
| 1    | 77895   | 3    |
| 2    | 44678   | 3    |
| 3    | 22456   | 1    |
| 4    | 24562   | 1    |
| 5    | 34764   | 15   |

```sql
SELECT Persons.LastName, Persons.FirstName, Orders.OrderNo
FROM Persons
FULL JOIN Orders ON Persons.P_Id = Orders.P_Id
ORDER BY Persons.LastName;
```

#### Result

| LastName  | FirstName | OrderNo |
|-----------|-----------|---------|
| Hansen    | Ola       | 22456   |
| Hansen    | Ola       | 24562   |
| Pettersen | Kari      | 77895   |
| Pettersen | Kari      | 44678   |
| Svendson  | Tove      | *null*  |
| *null*    | *null*    | 34764   |


## SQL CROSS JOIN

### Description:
- The `CROSS JOIN` keyword returns the Cartesian product of two tables.
- That means it will return all possible combinations of rows from both tables.

### Syntax:
```sql
SELECT column_name(s)
FROM table1
CROSS JOIN table2;
```

### Example:

**Table A:**

| ID | Name   |
|----|--------|
| 1  | Alice  |
| 2  | Bob    |

**Table B:**

| Dept |
|------|
| HR   |
| IT   |

**Query:**
```sql
SELECT A.Name, B.Dept
FROM A
CROSS JOIN B;
```

**Result:**

| Name  | Dept |
|-------|------|
| Alice | HR   |
| Alice | IT   |
| Bob   | HR   |
| Bob   | IT   |

---

## SQL SELF JOIN

### Description:
- A `SELF JOIN` is a regular join but the table is joined with itself.
- It is useful when there is a hierarchical or relational reference within the same table.

### Syntax:
```sql
SELECT A.column_name, B.column_name
FROM table_name A, table_name B
WHERE condition;
```

### Example:

**Employees Table:**

| EmpID | Name     | ManagerID |
|-------|----------|-----------|
| 1     | John     | NULL      |
| 2     | Alice    | 1         |
| 3     | Bob      | 1         |
| 4     | Charlie  | 2         |

**Query:**
```sql
SELECT E1.Name AS Employee, E2.Name AS Manager
FROM Employees E1
LEFT JOIN Employees E2
ON E1.ManagerID = E2.EmpID;
```

**Result:**

| Employee | Manager  |
|----------|----------|
| John     | NULL     |
| Alice    | John     |
| Bob      | John     |
| Charlie  | Alice    |

---

# Use of Joins in Complex Queries to Combine Data from Multiple Tables

In real-world applications, data is usually stored across multiple related tables in a database. **SQL Joins** are essential tools that help to **combine and retrieve related information from these tables efficiently**. This becomes especially important in complex queries where you need to fetch comprehensive data by merging multiple entities.

---

## Why Use Joins?

- To **avoid redundancy** by storing related data in separate tables.
- To **improve query performance** and ensure **normalized database design**.
- To **gather comprehensive data** from different tables using logical relationships.

---

## Example Scenario: Student Management System

### Tables:

#### Students

| StudentID | Name      | DepartmentID |
|-----------|-----------|--------------|
| 1         | Alice     | 10           |
| 2         | Bob       | 20           |
| 3         | Charlie   | 30           |

#### Departments

| DepartmentID | DepartmentName |
|--------------|----------------|
| 10           | Computer Sci   |
| 20           | Electronics    |
| 30           | Civil Engg     |

#### Marks

| MarkID | StudentID | Subject   | Score |
|--------|-----------|-----------|-------|
| 1      | 1         | DBMS      | 85    |
| 2      | 1         | OS        | 90    |
| 3      | 2         | DBMS      | 75    |
| 4      | 3         | OS        | 80    |

---

## Example 1: Fetch student names with their department and marks

```sql
SELECT 
  s.Name,
  d.DepartmentName,
  m.Subject,
  m.Score
FROM Students s
INNER JOIN Departments d ON s.DepartmentID = d.DepartmentID
INNER JOIN Marks m ON s.StudentID = m.StudentID
ORDER BY s.Name, m.Subject;
```

### Result

| Name    | DepartmentName | Subject | Score |
|---------|----------------|---------|-------|
| Alice   | Computer Sci    | DBMS    | 85    |
| Alice   | Computer Sci    | OS      | 90    |
| Bob     | Electronics     | DBMS    | 75    |
| Charlie | Civil Engg      | OS      | 80    |

---

## Example 2: List all students and their departments, even if they have no marks yet (LEFT JOIN)

```sql
SELECT 
  s.Name,
  d.DepartmentName,
  m.Subject,
  m.Score
FROM Students s
LEFT JOIN Departments d ON s.DepartmentID = d.DepartmentID
LEFT JOIN Marks m ON s.StudentID = m.StudentID
ORDER BY s.Name;
```

---

## Example 3: Find all departments and any students who belong to them (RIGHT JOIN)

```sql
SELECT 
  s.Name,
  d.DepartmentName
FROM Students s
RIGHT JOIN Departments d ON s.DepartmentID = d.DepartmentID
ORDER BY d.DepartmentName;
```

---

## Example 4: Using FULL JOIN to get all students and marks, even if a student has no marks or a mark record doesn’t match a student

```sql
SELECT 
  s.Name,
  m.Subject,
  m.Score
FROM Students s
FULL JOIN Marks m ON s.StudentID = m.StudentID
ORDER BY s.Name;
```

---

## Example 5: Complex join with aggregate function — Get average marks per department

```sql
SELECT 
  d.DepartmentName,
  AVG(m.Score) AS AverageScore
FROM Departments d
LEFT JOIN Students s ON d.DepartmentID = s.DepartmentID
LEFT JOIN Marks m ON s.StudentID = m.StudentID
GROUP BY d.DepartmentName;
```

### Result

| DepartmentName | AverageScore |
|----------------|--------------|
| Computer Sci   | 87.5         |
| Electronics    | 75           |
| Civil Engg     | 80           |

---

## Benefits of Using Joins in Complex Queries

- **Scalability:** Easily adaptable to additional tables (e.g., Attendance, Faculty).
- **Modularity:** Each table focuses on one aspect (students, marks, departments), maintaining clarity.
- **Flexibility:** You can perform filters, aggregations, and groupings using joined results.
- **Data Integrity:** Ensures data consistency by using foreign key relationships.

---

# SQL UNION and SELECT INTO Statements

## The SQL UNION Operator

- The `UNION` operator is used to combine the result sets of two or more `SELECT` statements.
- Each `SELECT` statement must:
  - Have the same number of columns.
  - Have columns with similar data types.
  - Have columns in the same order.

### Syntax

```sql
SELECT column_name(s) FROM table_name1
UNION
SELECT column_name(s) FROM table_name2;
```

- By default, `UNION` selects only distinct values.
- To include duplicate values, use `UNION ALL`.

### Syntax for UNION ALL

```sql
SELECT column_name(s) FROM table_name1
UNION ALL
SELECT column_name(s) FROM table_name2;
```

- Column names in the result set are taken from the first `SELECT` statement.

### Example

#### Tables:

**Employees_Norway**

| E_ID | E_Name            |
|------|-------------------|
| 01   | Hansen, Ola       |
| 02   | Svendson, Tove    |
| 03   | Svendson, Stephen |
| 04   | Pettersen, Kari   |

**Employees_USA**

| E_ID | E_Name            |
|------|-------------------|
| 01   | Turner, Sally     |
| 02   | Kent, Clark       |
| 03   | Svendson, Stephen |
| 04   | Scott, Stephen    |

```sql
SELECT E_Name FROM Employees_Norway
UNION
SELECT E_Name FROM Employees_USA;
```

#### Result:

```
Hansen, Ola
Svendson, Tove
Svendson, Stephen
Pettersen, Kari
Turner, Sally
Kent, Clark
Scott, Stephen
```

- Notice: Duplicates are removed (`Svendson, Stephen` appears only once).

### UNION ALL Example

```sql
SELECT E_Name FROM Employees_Norway
UNION ALL
SELECT E_Name FROM Employees_USA;
```

#### Result:

```
Hansen, Ola
Svendson, Tove
Svendson, Stephen
Pettersen, Kari
Turner, Sally
Kent, Clark
Svendson, Stephen
Scott, Stephen
```

---

## The SQL SELECT INTO Statement

- Used to create backup copies of tables.
- Selects data from one table and inserts it into a new table.

### Syntax

#### Select all columns into a new table

```sql
SELECT * INTO new_table_name FROM old_table_name;
```

#### Select specific columns

```sql
SELECT column1, column2 INTO new_table_name FROM old_table_name;
```

#### With external database (for MS Access)

```sql
SELECT * INTO new_table_name IN 'Backup.mdb' FROM old_table_name;
```

### Example: Make a Backup Copy

```sql
SELECT * INTO Persons_Backup FROM Persons;
```

#### Backup into another database

```sql
SELECT * INTO Persons_Backup IN 'Backup.mdb' FROM Persons;
```

#### Copy only some fields

```sql
SELECT LastName, FirstName INTO Persons_Backup FROM Persons;
```

### SELECT INTO with WHERE Clause

```sql
SELECT LastName, FirstName
INTO Persons_Backup
FROM Persons
WHERE City = 'Sandnes';
```

### SELECT INTO with JOIN

```sql
SELECT Persons.LastName, Orders.OrderNo
INTO Persons_Order_Backup
FROM Persons
INNER JOIN Orders ON Persons.P_Id = Orders.P_Id;
```

---

## The CREATE DATABASE Statement

- Used to create a database.

### Syntax

```sql
CREATE DATABASE database_name;
```

### Example

```sql
CREATE DATABASE my_db;
```

---

## The CREATE TABLE Statement

- Used to create a table in a database.

### Syntax

```sql
CREATE TABLE table_name (
    column1 data_type,
    column2 data_type,
    ...
);
```

### Example

```sql
CREATE TABLE Persons (
    P_Id int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```

#### Table Structure

| P_Id | LastName | FirstName | Address | City |
|------|----------|-----------|---------|------|

- Use `INSERT INTO` to add data.
---


# SQL Indexing and Performance Optimization

## What is an Index?

An **index** in SQL is a performance-tuning method of allowing faster retrieval of records from a table. Indexes are created on columns that are often used in `WHERE`, `JOIN`, `ORDER BY`, or `GROUP BY` clauses to speed up data access.

### Impact on Query Performance

- Indexes reduce the amount of data scanned during a query.
- Speed up data retrieval significantly.
- Can **slow down** data insertion, deletion, and updates because the index must also be updated.
- Improve JOIN and WHERE performance when used correctly.

---

##  Types of Indexes

### 1. **Single-column Indexes**
Indexes created on one column of a table.

#### Syntax:
```sql
CREATE INDEX index_name ON table_name (column_name);
```

#### Examples:
```sql
CREATE INDEX idx_lastname ON Employees (LastName);
CREATE INDEX idx_city ON Customers (City);
CREATE INDEX idx_order_date ON Orders (OrderDate);
```

---

### 2. **Composite Indexes (Multi-column Indexes)**
Indexes created on two or more columns of a table.

#### Syntax:
```sql
CREATE INDEX index_name ON table_name (column1, column2);
```

#### Examples:
```sql
CREATE INDEX idx_name_dob ON Persons (LastName, DateOfBirth);
CREATE INDEX idx_order_customer ON Orders (CustomerID, OrderDate);
CREATE INDEX idx_city_zip ON Customers (City, ZipCode);
```

**Note**: The order of columns matters. The index will only be used if the leading column is part of the query condition.

---

### 3. **Unique Indexes**
Ensure that all values in the indexed column(s) are unique.

#### Syntax:
```sql
CREATE UNIQUE INDEX index_name ON table_name (column_name);
```

#### Examples:
```sql
CREATE UNIQUE INDEX idx_email_unique ON Users (Email);
CREATE UNIQUE INDEX idx_username_unique ON Accounts (Username);
CREATE UNIQUE INDEX idx_empid_unique ON Employees (EmployeeID);
```

 Used to enforce constraints and maintain data integrity.

---

##  How Indexes are Stored and Retrieved

- SQL indexes are typically stored using **B-Trees** (Balanced Tree structures).
- Each node contains keys and pointers to data blocks or other tree nodes.
- Searching through the index is like performing a binary search: faster than scanning row by row.
- Some databases (like PostgreSQL) also support **Hash Indexes** or **GIN/GiST Indexes** for full-text search and JSONB types.

---

##  Deleting Indexes

### Syntax (MySQL):
```sql
ALTER TABLE table_name DROP INDEX index_name;
```

### Example:
```sql
ALTER TABLE Customers DROP INDEX idx_city;
```

---

##  Best Practices

- Use indexes on columns that are frequently searched or used in JOINs.
- Avoid over-indexing: it can degrade performance on `INSERT`, `UPDATE`, and `DELETE`.
- Composite indexes should be created only when necessary.
- Use **EXPLAIN** or **QUERY PLAN** to analyze index usage.

---

##  Summary

| Type              | Columns Involved      | Allows Duplicates | Use Case                                 |
|-------------------|-----------------------|-------------------|------------------------------------------|
| Single-column     | 1                     | Yes               | Search/filter on a single column         |
| Composite         | 2 or more             | Yes               | Filters with multiple columns            |
| Unique            | 1 or more             | No                | Enforce uniqueness (like primary key)    |

---

# ACID Properties

## Overview

A transaction in a Database Management System (DBMS) is a single logical unit of work that accesses and possibly alters the contents of a database. Transactions use read-and-write operations to manage data. Certain properties are adhered to in order to ensure database consistency before and after a transaction. These properties are known as ACID properties.

![image](https://github.com/user-attachments/assets/a40ca95c-403c-43cb-b866-323e1d7ab55f)

---

## ACID Properties Overview

### 1. Atomicity

- Atomicity means that either the entire transaction is executed, or none of it is. There is no partial execution.
- Each transaction is seen as a single unit that either completes fully or does not execute at all.

**Operations:**
- Abort: If a transaction aborts, any changes made to the database are not visible.
- Commit: If a transaction is committed, the changes made are visible.

Atomicity is also known as the "All or nothing rule."

### Example

**Scenario:** Transfer ₹100 from Account A to Account B.

**Steps:**
1. Deduct ₹100 from Account A.
2. Add ₹100 to Account B.

**Case 1: Success**
- Account A: ₹1000 → ₹900
- Account B: ₹500 → ₹600
- All steps complete and changes are committed.

**Case 2: Failure After Step 1**
- ₹100 deducted from A but not added to B.
- System crash or error occurs.

**Without Atomicity:**
- A = ₹900, B = ₹500 → Inconsistent state.

**With Atomicity:**
- Entire transaction is rolled back.
- A = ₹1000, B = ₹500 → Original state preserved.

**Conclusion:** Atomicity ensures that either all operations in a transaction are completed or none are, preventing partial updates.


---

### 2. Consistency

- Consistency means that integrity constraints must be maintained so that the database remains consistent before and after the transaction.
- It ensures the correctness of the database.

### Consistency Example

**Scenario:** Transfer £100 from Account X to Account Y.

**Initial Balances:**
- Account X: £500
- Account Y: £200
- Total: £700

**After Transaction:**
- Account X: £400
- Account Y: £300
- Total: £700

**Explanation:**  
The total amount before and after the transaction remains the same, preserving database integrity. If the transaction fails midway, the totals would differ, causing inconsistency.

**Conclusion:**  
Consistency ensures the database remains in a valid state by enforcing all integrity constraints before and after a transaction.


---

### 3. Isolation

- Isolation ensures that multiple transactions can occur concurrently without causing database inconsistency.
- Transactions operate independently without interference.
- Changes made in a transaction are not visible to others until committed.

### Isolation Example

**Scenario:** Two transactions T and T' run concurrently on accounts X and Y, both initially £500.

- T reads and modifies Y.
- T' starts before T commits.

**Problem Without Isolation:**
- T' reads old value of Y (before T’s update).
- Leads to inconsistent computations, e.g., T' sums X + Y = 500 + 500 = 1000, but after T commits, Y has changed, so the real sum should differ.

**With Isolation:**
- Changes made by T are not visible to T' until T commits.
- Each transaction operates independently, preventing inconsistency.

**Conclusion:**  
Isolation ensures concurrent transactions do not interfere, maintaining database consistency.


---

### 4. Durability

- Durability guarantees that once a transaction has been completed, its updates are stored on disk and persist even in the case of a system failure.

### Durability Example

**Scenario:** Transferring £100 from Account X to Account Y.

- The transaction is committed, updating both accounts.
- Immediately after, the system crashes.

**With Durability:**

- Changes made by the committed transaction are saved permanently.
- After system recovery, the updates (transfer of £100) remain intact.

**Conclusion:**  
Durability guarantees that once a transaction is committed, its results persist even if the system fails.


---

## Advantages of ACID Properties in DBMS

- Data Consistency: Maintains consistent and accurate data after transaction execution.
- Data Integrity: Ensures that changes to the database are permanent.
- Concurrency Control: Manages multiple transactions simultaneously without interference.
- Recovery: Enables the system to recover data up to the point of failure.

---

## Disadvantages of ACID Properties in DBMS

- Performance: Can introduce performance overhead due to additional processing.
- Scalability: May pose challenges in scaling large distributed systems.
- Complexity: Implementation can be complex and resource-intensive.

---


# SQL Transaction Control Commands

Transaction control commands in SQL manage the execution and integrity of transactions, allowing control over when changes are made permanent or undone in the database. These commands ensure data consistency, reliability, and proper handling of concurrent transactions.

---

## 1. BEGIN TRANSACTION

- Marks the start of a new transaction.
- All subsequent SQL statements belong to this transaction until a `COMMIT` or `ROLLBACK` is issued.
- Does not alter the database itself, just begins transaction scope.

**Syntax:**
```sql
BEGIN TRANSACTION transaction_name;
```

**Example: Bank Transfer**
```sql
BEGIN TRANSACTION;

UPDATE Accounts
SET Balance = Balance - 150
WHERE AccountID = 'A';

UPDATE Accounts
SET Balance = Balance + 150
WHERE AccountID = 'B';

COMMIT;
```

- If an error occurs during the transaction, `ROLLBACK` can undo all changes to avoid inconsistency (e.g., deducting from one account without crediting another).

---

## 2. COMMIT

- Saves all changes made during the current transaction permanently to the database.
- Once committed, changes cannot be undone.

**Syntax:**
```sql
COMMIT;
```

###Example
Here is the sample Student table that will be used to perform the operations in this example. This table contains basic student details such as ID, name, age, and other relevant information that will be manipulated using various transaction control commands.

![image](https://github.com/user-attachments/assets/53f2cee8-ae25-4358-8917-3b77d735e92f)

Following is an example which would delete those records from the table which have age = 20 and then COMMIT the changes in the database. 

```sql
DELETE FROM Student WHERE AGE = 20;
COMMIT;
```
###Output

![image](https://github.com/user-attachments/assets/266b1441-89cb-407f-9de4-2970da3fa6f3)

---

## 3. ROLLBACK

- Undoes all changes made in the current transaction.
- Reverts the database to the state before `BEGIN TRANSACTION`.
- Used when errors occur or to abort a transaction.

**Syntax:**
```sql
ROLLBACK;
```

**Example:**

Delete those records from the table which have age = 20 and then ROLLBACK the changes in the database. In this case, the DELETE operation is undone, and the changes to the database are not saved.

```sql
DELETE FROM Student WHERE AGE = 20;
ROLLBACK;
```

![image](https://github.com/user-attachments/assets/2b2e379a-617d-4e5c-af0a-c09ce53d4865)

---

## 4. SAVEPOINT

- Creates a named checkpoint inside a transaction.
- Allows partial rollback to the savepoint without rolling back the entire transaction.

**Syntax:**
```sql
SAVEPOINT savepoint_name;
```

**Example:**
```sql
SAVEPOINT SP1;

DELETE FROM Student WHERE AGE = 20;
//deleted
SAVEPOINT SP2; //Savepoint created.
```
###Output

![image](https://github.com/user-attachments/assets/68090955-05c6-4d59-bd9c-be8eb5f97bcf)

###Explaination

From the above example Sample table1, Delete those records from the table which have age = 20 and then ROLLBACK the changes in the database by keeping Savepoints. Here SP1 is first SAVEPOINT created before deletion. In this example one deletion have taken place. After deletion again SAVEPOINT SP2 is created. 
---

## 5. ROLLBACK TO SAVEPOINT

- Rolls back changes made after the specified savepoint.
- Keeps changes made before the savepoint intact.

**Syntax:**
```sql
ROLLBACK TO SAVEPOINT savepoint_name;
```

**Example:**

Deletion have been taken place, let us assume that we have changed our mind and decided to ROLLBACK to the SAVEPOINT that we identified as SP1 which is before deletion. So, In this case the DELETE operation is undone, and the transaction is returned to the state it was in at the SP1 savepoint

```sql
ROLLBACK TO SP1; //Rollback completed
```

![image](https://github.com/user-attachments/assets/afe50928-30c1-4848-ac7d-d53c87205495)

---

## 6. RELEASE SAVEPOINT

- Removes a previously created savepoint.
- After releasing, cannot roll back to that savepoint anymore.

**Syntax:**
```sql
RELEASE SAVEPOINT savepoint_name;
```

**Example:**

Once the savepoint SP2 is released, we can no longer roll back to it.

```sql
RELEASE SAVEPOINT SP2; -- Release the second savepoint.
```

---

# Why Use Transactions in Banking?

- Without transactions, inconsistent states can occur (e.g., money deducted from one account but not added to another).
- Transactions ensure atomicity: both operations succeed or both fail.

---

# Types of SQL Transactions

1. **Read Transactions:** Only perform data retrieval (`SELECT`).
2. **Write Transactions:** Modify data (`INSERT`, `UPDATE`, `DELETE`).
3. **Distributed Transactions:** Span multiple databases, ensuring consistency.
4. **Implicit Transactions:** Automatically started by the DBMS for certain operations.
5. **Explicit Transactions:** Manually controlled by the user via `BEGIN TRANSACTION`, `COMMIT`, and `ROLLBACK`.

---

# Handling Concurrent Transactions and Isolation Levels

- **Concurrency:** Multiple transactions often run simultaneously.
- **Problem:** Without control, concurrent transactions may interfere, causing inconsistent or incorrect data.

---

## Isolation

- Ensures transactions operate independently, without seeing uncommitted changes from others.
- Changes are visible to other transactions only after a commit.

---

## Isolation Levels

Databases provide different isolation levels balancing consistency and performance:

| Level             | Description                                                                 | Possible Issues Prevented              |
|-------------------|-----------------------------------------------------------------------------|--------------------------------------|
| Read Uncommitted  | Allows reading uncommitted changes (dirty reads).                           | None (can see dirty reads)            |
| Read Committed    | Only reads committed data. Prevents dirty reads.                           | Dirty reads                          |
| Repeatable Read   | Ensures repeated reads of the same data return the same results.           | Dirty reads, Non-repeatable reads    |
| Serializable      | Highest isolation. Transactions appear sequential.                         | Dirty reads, Non-repeatable reads, Phantom reads |

---

## Best Practices for Handling Transactions and Isolation

- **Keep transactions short:** Avoid long transactions that hold locks for too long.
- **Use proper indexing:** Improves query speed, reducing lock time.
- **Avoid unnecessary locks:** Prevent blocking other transactions.
- **Commit early:** Releases locks and resources quickly.
- **Choose isolation levels wisely:** Based on application requirements for consistency and concurrency.

---

# Monitoring and Optimizing SQL Transactions

- **Monitor Locks:** Identify and reduce locking conflicts.
- **Limit Transaction Scope:** Process smaller datasets per transaction.
- **Batch Processing:** Break large operations into smaller batches to prevent system overload.

---


# Practice Task: SQL 

## 1. Write Queries Involving Multiple JOINs

### Example Schema:
```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    ClassID INT
);

CREATE TABLE Classes (
    ClassID INT PRIMARY KEY,
    ClassName VARCHAR(100),
    TeacherID INT
);

CREATE TABLE Teachers (
    TeacherID INT PRIMARY KEY,
    TeacherName VARCHAR(100)
);
```

### Task:
Write a query to display each student's name, their class name, and the teacher's name.

### Example Query:
```sql
SELECT 
    Students.Name AS StudentName,
    Classes.ClassName,
    Teachers.TeacherName
FROM Students
JOIN Classes ON Students.ClassID = Classes.ClassID
JOIN Teachers ON Classes.TeacherID = Teachers.TeacherID;
```

---

## 2. Implement and Analyze the Effect of Indexes on Query Speed

### Create Sample Table:
```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerName VARCHAR(100),
    OrderDate DATE,
    TotalAmount DECIMAL(10, 2)
);
```

### Insert Many Rows (for testing):
```sql
-- Assume a script or loop to insert 100,000+ rows
```

### Without Index:
```sql
SELECT * FROM Orders WHERE CustomerName = 'John Doe';
```

### Add Index:
```sql
CREATE INDEX idx_customer_name ON Orders(CustomerName);
```

### With Index:
```sql
SELECT * FROM Orders WHERE CustomerName = 'John Doe';
```

**Observe:** The performance difference when executing the query before and after adding the index.

---

## 3. Implement Transactions with COMMIT and ROLLBACK

### Scenario: Bank Account Transfer
```sql
BEGIN TRANSACTION;

-- Deduct from Account A
UPDATE Accounts SET Balance = Balance - 100 WHERE AccountID = 'A';

-- Add to Account B
UPDATE Accounts SET Balance = Balance + 100 WHERE AccountID = 'B';

-- If all is well, COMMIT
COMMIT;
```

### If something goes wrong:
```sql
ROLLBACK;
```

### Using SAVEPOINT:
```sql
BEGIN TRANSACTION;

SAVEPOINT BeforeTransfer;

-- Try to deduct amount
UPDATE Accounts SET Balance = Balance - 100 WHERE AccountID = 'A';

-- Something fails here...

ROLLBACK TO BeforeTransfer;

COMMIT;
```

---

**Conclusion:** 
These practical tasks help you understand how JOINs combine data, how indexes affect query speed, and how transactions ensure data consistency and reliability in SQL databases.
