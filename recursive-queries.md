# PostgreSQL Recursive Queries

## 1. What is Recursion?

Recursion is a process where a query repeatedly executes using the results from its previous execution.

In PostgreSQL, we use `WITH RECURSIVE` to perform recursive queries.

**Use cases:**
- Hierarchical data
- Employee-manager relationships
- Family trees
- Recommendation chains
- Folder structures

## 2. Syntax of Recursive CTE

```sql
WITH RECURSIVE cte_name AS (

    -- Anchor query
    SELECT ...

    UNION ALL

    -- Recursive query
    SELECT ...
    FROM cte_name
    JOIN ...

)
SELECT * FROM cte_name;
```

## 3. Three Main Components

### 1. Anchor Query
- Executes first.
- Defines the starting point.
- Does not reference the recursive CTE.

### 2. Recursive Query
- References the CTE itself.
- Uses previously generated rows to find new rows.
- Continues executing until no more rows are returned.

### 3. Termination Condition
- Determines when recursion stops.
- Recursion stops when the recursive query returns no rows.
- A missing stopping condition can cause infinite recursion.

## 4. Example: Generate Numbers

```sql
WITH RECURSIVE numbers(num) AS (
    SELECT 1

    UNION ALL

    SELECT num + 1
    FROM numbers
    WHERE num < 5
)
SELECT * FROM numbers;
```

**Output:**

```text
 num
-----
  1
  2
  3
  4
  5
```

## 5. How Does It Execute?

| Execution | Result |
|---|---:|
| Anchor query | 1 |
| Iteration 1 | 2 |
| Iteration 2 | 3 |
| Iteration 3 | 4 |
| Iteration 4 | 5 |
| Iteration 5 | Stops |

## 6. Important Keywords

| Keyword | Purpose |
|---|---|
| `WITH RECURSIVE` | Enables recursive CTEs |
| `UNION ALL` | Combines anchor and recursive results, retaining duplicates |
| `JOIN` | Finds related records |
| `WHERE` | Applies conditions to control recursion |
| `SELECT` | Retrieves the final result |

## 7. UNION vs UNION ALL

- `UNION`: Removes duplicate rows.
- `UNION ALL`: Retains duplicate rows.

`UNION ALL` is commonly used in recursive queries.

## 8. Important Things to Remember

- Every recursive CTE needs an anchor query.
- The recursive query references the CTE itself.
- Anchor and recursive queries must return compatible columns and data types.
- Each iteration works with rows produced by the previous iteration.
- Recursion stops when no new rows are returned.
- Cycles can cause endless recursion when not handled.
- PostgreSQL supports cycle detection using the `CYCLE` clause.

## 9. References

- [PostgreSQL Recursive Queries Documentation](https://www.postgresql.org/docs/current/queries-with.html)
- [PGExercises – Recursive Queries](https://pgexercises.com/questions/recursive/)
