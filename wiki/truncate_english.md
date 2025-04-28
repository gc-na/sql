<!--
Meta Description: # SQL TRUNCATE Command: Efficiently Remove Data from Tables ## Synopsis The SQL TRUNCATE command is a Data Definition Language (DDL) operation used to...
Meta Keywords: truncate, table, sql, command, key
-->

# SQL TRUNCATE Command: Efficiently Remove Data from Tables

## Synopsis
The SQL TRUNCATE command is a Data Definition Language (DDL) operation used to quickly delete all rows from a table while maintaining its structure for future use. Unlike the DELETE command, TRUNCATE is faster and does not log individual row deletions.

## Documentation
### Purpose
The TRUNCATE command serves the purpose of efficiently emptying a table without removing the table itself. It is particularly useful when you need to reset a table to its initial state without dropping and recreating it.

### Usage
The basic syntax for the TRUNCATE command is:

```sql
TRUNCATE TABLE table_name;
```

**Key Characteristics:**
- **Performance**: TRUNCATE is typically faster than DELETE because it does not generate individual row delete logs.
- **Reset Identity**: If the table contains an identity column, TRUNCATE will reset the identity value back to the seed value defined for the column.
- **No WHERE Clause**: TRUNCATE cannot be used with a WHERE clause; it will remove all records from the table.
- **Transaction Log**: Unlike DELETE, which logs each row deletion, TRUNCATE logs the deallocation of the data pages, making it more efficient for large tables.

### Considerations
- **Permissions**: To execute TRUNCATE, the user must have the DROP privilege on the table.
- **Foreign Key Constraints**: If a table has foreign key constraints, TRUNCATE cannot be executed on that table until the constraints are removed or the referencing tables are truncated as well.

## Examples
### Example 1: Basic TRUNCATE Usage
To remove all records from a table named `employees`:

```sql
TRUNCATE TABLE employees;
```

### Example 2: Resetting an Identity Column
After truncating the `orders` table, the identity column will reset:

```sql
TRUNCATE TABLE orders;
```

### Example 3: Truncating a Table with Foreign Key Constraints
Before truncating a table with foreign key constraints, you must drop or disable the constraints. For example:

```sql
ALTER TABLE order_items DROP CONSTRAINT fk_order;
TRUNCATE TABLE orders;
```

## Explanation
### Common Pitfalls
- **Non-Reversible**: Unlike DELETE, TRUNCATE cannot be rolled back if the command is executed outside of a transaction. This means once you truncate a table, the data is lost permanently unless you have backups.
- **Restrictions with Foreign Keys**: Attempting to truncate a table that is referenced by a foreign key constraint will lead to an error. Always check for relationships before using TRUNCATE.

### Additional Notes
- TRUNCATE does not fire triggers that would normally execute on record deletion.
- It is important to understand that TRUNCATE is a DDL operation and will commit the transaction immediately; hence, it cannot be undone within the same transaction context.

## One Line Summary
The TRUNCATE command in SQL is a fast and efficient way to remove all records from a table while preserving its structure, but it cannot be undone and has restrictions with foreign key constraints.