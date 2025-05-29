# Week 4: Views, Stored Procedures (PL/SQL), and Query Optimization

## 1. Views

### What is a View?
- A **view** is a virtual table created from a SQL query.
- It does not store data itself but shows data from base tables.

### Advantages of Views
- Simplifies complex queries.
- Restricts access to sensitive data.
- Enhances security and abstraction.
- Reusability of queries.

### Creating a View
```sql
CREATE VIEW dept_sales AS
SELECT emp_name, salary FROM employees WHERE department = 'Sales';
```

### Querying a View
```sql
SELECT * FROM dept_sales;
```

### Modifying a View
```sql
CREATE OR REPLACE VIEW dept_sales AS
SELECT emp_name, salary FROM employees WHERE department = 'Marketing';
```

### Dropping a View
```sql
DROP VIEW dept_sales;
```

---

## 2. PL/SQL: Stored Procedures and Functions

### What is PL/SQL?
- **PL/SQL (Procedural Language/SQL)** is Oracle’s procedural extension to SQL.
- Allows use of variables, loops, conditions, and exceptions with SQL.


### PL/SQL Block Structure
```sql
DECLARE
   -- variable declarations
BEGIN
   -- executable statements
EXCEPTION
   -- error handling
END;
```


### PL/SQL Data Types

| Data Type     | Description                                |
|---------------|--------------------------------------------|
| `NUMBER`      | Numeric values (integers, floats)          |
| `VARCHAR2(n)` | Variable-length character strings          |
| `CHAR(n)`     | Fixed-length character strings             |
| `DATE`        | Date and time values                       |
| `BOOLEAN`     | Logical values (`TRUE`, `FALSE`, `NULL`)   |
| `%TYPE`       | Derives data type from a column/variable   |
| `%ROWTYPE`    | Derives structure from a table row         |


### Variable Declaration and Assignment
```sql
DECLARE
   emp_name VARCHAR2(50);
   emp_id employees.emp_id%TYPE;
   hire_date DATE := SYSDATE;
BEGIN
   emp_name := 'Alice';
   DBMS_OUTPUT.PUT_LINE(emp_name);
END;
```

To enable output:
```sql
SET SERVEROUTPUT ON;
```

---

### Conditional Statements
```sql
IF salary > 50000 THEN
   DBMS_OUTPUT.PUT_LINE('High Salary');
ELSIF salary = 50000 THEN
   DBMS_OUTPUT.PUT_LINE('Average Salary');
ELSE
   DBMS_OUTPUT.PUT_LINE('Low Salary');
END IF;
```


### Loop Structures

**FOR Loop:**
```sql
FOR i IN 1..5 LOOP
   DBMS_OUTPUT.PUT_LINE(i);
END LOOP;
```

**WHILE Loop:**
```sql
WHILE i <= 5 LOOP
   DBMS_OUTPUT.PUT_LINE(i);
   i := i + 1;
END LOOP;
```

**SIMPLE Loop:**
```sql
LOOP
   EXIT WHEN counter > 10;
   counter := counter + 1;
END LOOP;
```


### Exception Handling
```sql
BEGIN
   -- code that may raise exception
EXCEPTION
   WHEN NO_DATA_FOUND THEN
      DBMS_OUTPUT.PUT_LINE('No data found');
   WHEN OTHERS THEN
      DBMS_OUTPUT.PUT_LINE('Other error');
END;
```


### Stored Procedures

#### Creating a Procedure
```sql
CREATE OR REPLACE PROCEDURE greet(p_name IN VARCHAR2) IS
BEGIN
   DBMS_OUTPUT.PUT_LINE('Hello, ' || p_name);
END;
```

#### Executing a Procedure
```sql
EXEC greet('John');
```


### Functions

#### Creating a Function
```sql
CREATE OR REPLACE FUNCTION get_square(p_num IN NUMBER)
RETURN NUMBER IS
BEGIN
   RETURN p_num * p_num;
END;
```

#### Using the Function
```sql
SELECT get_square(5) FROM dual;
```


### Differences: Procedure vs Function

| Feature                | Procedure                 | Function                     |
|------------------------|---------------------------|------------------------------|
| Return Value           | No (or via OUT parameter) | Yes (via RETURN)             |
| Use in SQL Queries     | No                        | Yes                          |
| Use Case               | Perform task              | Compute and return value     |

---

## 3. Query Optimization

### Importance of Query Optimization
- **Improves query execution speed** and reduces resource consumption.
- Vital for **scalability** and **performance** in large applications.
- Critical skill tested in **technical interviews** and used in real-world database systems.


### Using `EXPLAIN` to Understand Query Plans
- `EXPLAIN` (MySQL) or `EXPLAIN PLAN` (Oracle/PostgreSQL) helps analyze how a query is executed.

#### Example:
```sql
EXPLAIN SELECT name FROM employees WHERE salary > 50000;
```

#### Key Output Columns (MySQL):
- **id**: Order of query execution
- **select_type**: Type of SELECT (e.g., SIMPLE, PRIMARY)
- **table**: Table accessed
- **type**: Access method (e.g., ALL, index, range)
- **key**: Index used
- **rows**: Estimated rows scanned
- **Extra**: Additional info (e.g., Using where, Using index)


### Basic Optimization Techniques

1. **Use Indexes Appropriately**
   - Create indexes on columns used in `WHERE`, `JOIN`, `ORDER BY`.
   - Avoid indexing low-cardinality columns (e.g., gender).

2. **Avoid SELECT *** 
   - Fetch only required columns to reduce I/O and memory usage.

3. **Use WHERE Conditions Efficiently**
   - Filter early to reduce number of rows processed.

4. **Avoid Functions on Indexed Columns**
   - Example: `WHERE UPPER(name) = 'JOHN'` disables index usage.

5. **Use Joins Smartly**
   - Prefer explicit JOIN syntax over implicit joins.
   - Use INNER JOINs where possible to reduce result set size.

6. **Pagination and Limits**
   - Use `LIMIT` or `ROWNUM` to limit data retrieval for user interfaces.

7. **Avoid Subqueries When Possible**
   - Rewrite using JOINs if they offer better performance.


### Writing Efficient SQL Queries
- Keep queries **simple and readable**.
- Break down complex queries using **views or subqueries**.
- Use `EXISTS` instead of `IN` for large datasets.
- Ensure **consistent data types** in JOINs to avoid implicit conversions.
- Regularly **analyze and monitor performance** using EXPLAIN or profiling tools.

---
