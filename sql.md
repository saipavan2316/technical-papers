# SQL Concepts – Technical Paper

## 1. Introduction

A Database Management System (DBMS) is software used to store, manage, retrieve, and organize data efficiently. Relational databases such as PostgreSQL, MySQL, and Oracle store information in tables consisting of rows and columns.

Understanding database concepts helps developers build applications that are reliable, efficient, and scalable.

This paper covers important database concepts, including ACID, CAP Theorem, Joins, Aggregations, Normalization, Indexes, Transactions, Locking, Isolation Levels, and Triggers.

## 2. ACID Properties

ACID represents four properties that ensure reliable database transactions.

- **Atomicity:** A transaction is completed entirely or not executed at all.
- **Consistency:** A transaction maintains database rules and constraints.
- **Isolation:** Concurrent transactions do not interfere with each other incorrectly.
- **Durability:** Once committed, changes remain permanent even after system failures.

**Example: Bank Transfer**

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 1000
WHERE account_id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE account_id = 2;

COMMIT;
```

If an operation fails, `ROLLBACK` can undo the uncommitted changes.

ACID is essential for banking, payment systems, and applications requiring data accuracy.

## 3. CAP Theorem

CAP Theorem explains the trade-offs in distributed database systems.

CAP stands for:

- **Consistency:** Every successful read receives the latest written value.
- **Availability:** Every request receives a response from a functioning node.
- **Partition Tolerance:** The system continues operating despite network communication failures between nodes.

When a network partition occurs, a distributed system must choose between consistency and availability.

| Type | Description |
|---|---|
| CP | Prioritizes consistency over availability during a partition |
| AP | Prioritizes availability and may allow temporary inconsistencies |
| CA | Provides consistency and availability when there is no partition |

Examples include etcd and ZooKeeper for CP-oriented systems and Cassandra for configurable availability-oriented behavior.

## 4. SQL Joins

Joins combine data from multiple tables using related columns.

Consider two tables: Employees and Departments.

**INNER JOIN:** Returns only matching records.

```sql
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;
```

**LEFT JOIN:** Returns all records from the left table and matching records from the right table.

**RIGHT JOIN:** Returns all records from the right table and matching records from the left table.

**FULL OUTER JOIN:** Returns all records from both tables, including unmatched records.

**CROSS JOIN:** Returns every possible combination of rows from both tables.

**SELF JOIN:** Joins a table with itself, useful for employee-manager relationships.

Joins are commonly used to retrieve related information stored in different database tables.

## 5. Aggregations and Filters

Aggregate functions perform calculations on multiple rows.

Common aggregate functions:

| Function | Purpose |
|---|---|
| COUNT() | Counts rows or non-NULL values |
| SUM() | Calculates the total |
| AVG() | Calculates the average |
| MIN() | Finds the minimum value |
| MAX() | Finds the maximum value |

**GROUP BY:** Groups rows with matching values.

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department;
```

**WHERE:** Filters individual rows before grouping.

```sql
SELECT *
FROM employees
WHERE salary > 30000;
```

**HAVING:** Filters groups after aggregation.

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 40000;
```

Other important clauses:

- `ORDER BY` – Sorts results.
- `LIMIT` – Restricts the number of returned rows.
- `DISTINCT` – Removes duplicate results.

## 6. Database Normalization

Normalization is the process of organizing database tables to reduce data redundancy and prevent insertion, update, and deletion anomalies.

Important normal forms:

- **1NF:** Each column contains atomic values, with no repeating groups.
- **2NF:** Must satisfy 1NF and have no partial dependency on a composite candidate key.
- **3NF:** Must satisfy 2NF and eliminate inappropriate transitive dependencies of non-key attributes.
- **BCNF:** Every determinant must be a superkey.

**Example:**

Instead of storing employee and department information repeatedly in one table, separate them into:

1. Employees table – Employee details and department ID.
2. Departments table – Department ID and department name.

This reduces duplication and improves data consistency.

## 7. Database Indexes

An index is a database structure that improves the speed of data retrieval.

Without an index, the database may scan the entire table to find specific records.

**Creating an index in PostgreSQL:**

```sql
CREATE INDEX idx_employee_id
ON employees(employee_id);
```

Now queries filtering by employee ID may retrieve records faster.

Common index types:

- **B-Tree:** Supports equality, range queries, and sorting.
- **Hash:** Primarily supports equality comparisons.
- **Composite:** Uses multiple columns.
- **Unique:** Prevents duplicate indexed values.
- **Partial:** Indexes only rows satisfying a specified condition.

**Advantages:**
- Faster searches.
- Improved query performance.
- Efficient filtering and sorting.

**Disadvantages:**
- Requires additional storage.
- Can slow down INSERT, UPDATE, and DELETE operations.
- Requires maintenance.

Indexes should be created on columns frequently used in searches, joins, and sorting.

## 8. Database Transactions

A transaction is a group of database operations treated as one logical unit.

Important transaction commands:

| Command | Purpose |
|---|---|
| BEGIN | Starts a transaction |
| COMMIT | Saves changes permanently |
| ROLLBACK | Cancels uncommitted changes |
| SAVEPOINT | Creates a point for partial rollback |

**Example:**

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 1000
WHERE account_id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE account_id = 2;

COMMIT;
```

Transactions help maintain data integrity and prevent incomplete operations.

## 9. Locking Mechanisms

Locking controls simultaneous access to database records when multiple transactions operate on the same data.

Main types:

- **Shared Lock:** Allows multiple transactions to read data while preventing conflicting modifications.
- **Exclusive Lock:** Prevents conflicting access while a transaction modifies data.
- **Row-Level Lock:** Locks specific rows.
- **Table-Level Lock:** Locks an entire table.

**Example in PostgreSQL:**

```sql
BEGIN;

SELECT *
FROM accounts
WHERE account_id = 1
FOR UPDATE;

COMMIT;
```

`FOR UPDATE` locks the selected row against conflicting updates until the transaction ends.

**Deadlock:** Occurs when two or more transactions wait for locks held by each other. PostgreSQL detects deadlocks and aborts one transaction to resolve the situation.

PostgreSQL also uses MVCC (Multi-Version Concurrency Control) to allow readers and writers to work concurrently in many situations.

## 10. Database Isolation Levels

Isolation levels determine how transactions interact when multiple users access the database simultaneously.

Three common concurrency problems are:

- **Dirty Read:** Reading uncommitted changes from another transaction.
- **Non-Repeatable Read:** Reading the same row twice and receiving different values.
- **Phantom Read:** Repeating a query and receiving a different set of rows because another transaction inserted or deleted matching records.

Four standard isolation levels:

| Isolation Level | Description |
|---|---|
| Read Uncommitted | Allows dirty reads in standard SQL |
| Read Committed | Reads only committed data |
| Repeatable Read | Maintains a consistent snapshot during the transaction |
| Serializable | Provides behavior equivalent to serial transaction execution |

**PostgreSQL Note:**

- Read Committed is the default isolation level.
- Read Uncommitted behaves like Read Committed.
- Repeatable Read prevents phantom reads in PostgreSQL.
- Serializable provides the strongest isolation guarantees but may require transaction retries.

Example:

```sql
BEGIN TRANSACTION
ISOLATION LEVEL SERIALIZABLE;

SELECT *
FROM employees;

COMMIT;
```

## 11. Database Triggers

A trigger is a database mechanism that automatically executes a function when a specified event occurs.

Common trigger events:

- INSERT
- UPDATE
- DELETE

Types of triggers:

- **BEFORE:** Executes before the database operation.
- **AFTER:** Executes after the database operation.
- **INSTEAD OF:** Executes instead of an operation, commonly on views in PostgreSQL.

**Example:**

A trigger can automatically record employee salary changes in an audit table.

```sql
CREATE TRIGGER salary_update_trigger
AFTER UPDATE OF salary
ON employees
FOR EACH ROW
EXECUTE FUNCTION log_salary_changes();
```

In PostgreSQL, a trigger function must be created separately using PL/pgSQL.

**Advantages:**
- Automates database operations.
- Maintains audit records.
- Helps enforce database-level rules.

**Disadvantages:**
- Can make debugging difficult.
- May affect performance.
- Can introduce unexpected side effects.

## 12. Conclusion

Database concepts are essential for building reliable and efficient applications.

- ACID ensures reliable transactions.
- CAP explains distributed database trade-offs.
- Joins combine related information.
- Aggregations and filters help analyze data.
- Normalization reduces redundancy.
- Indexes improve query performance.
- Transactions execute operations reliably.
- Locking controls concurrent access.
- Isolation levels manage transaction interactions.
- Triggers automate database operations.

Understanding these concepts provides a strong foundation for SQL, database management, and backend development.

## 13. References

1. PostgreSQL Official Documentation – https://www.postgresql.org/docs/
2. Database System Concepts – Abraham Silberschatz, Henry F. Korth, and S. Sudarshan.
3. Fundamentals of Database Systems – Ramez Elmasri and Shamkant B. Navathe.
