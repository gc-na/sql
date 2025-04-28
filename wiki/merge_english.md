<!--
Meta Description: # Understanding SQL MERGE: The Ultimate Guide to Upsert Operations ## Synopsis The SQL MERGE statement is a powerful command that allows users to perf...
Meta Keywords: source, target, merge, when, matched
-->

# Understanding SQL MERGE: The Ultimate Guide to Upsert Operations

## Synopsis
The SQL MERGE statement is a powerful command that allows users to perform "upsert" operations—combining INSERT, UPDATE, and DELETE actions in a single statement. This functionality is particularly useful for synchronizing data between tables or updating records based on specific conditions.

## Documentation
### Purpose
The MERGE command is designed to streamline data manipulation by allowing users to conditionally insert, update, or delete records in a target table based on the results of a join with a source table. This reduces the need for multiple statements and enhances performance by minimizing the number of database calls.

### Usage
The basic syntax of the MERGE statement is as follows:

```sql
MERGE INTO target_table AS target
USING source_table AS source
ON target.key_column = source.key_column
WHEN MATCHED THEN
    UPDATE SET target.column1 = source.column1, target.column2 = source.column2
WHEN NOT MATCHED THEN
    INSERT (target.column1, target.column2) VALUES (source.column1, source.column2)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

### Details
- **MERGE INTO**: Specifies the target table that will be modified.
- **USING**: Defines the source table that will provide the data for the upsert operation.
- **ON**: Specifies the condition for matching records between the target and source tables.
- **WHEN MATCHED**: Defines the actions to take when a match is found; typically an UPDATE.
- **WHEN NOT MATCHED**: Specifies actions to take if no match is found; typically an INSERT.
- **WHEN NOT MATCHED BY SOURCE**: Allows for the deletion of records in the target table that no longer exist in the source table.

The MERGE statement supports transactions, ensuring that all operations are executed atomically.

## Examples
### Example 1: Basic MERGE Operation
Suppose we have a target table `employees` and a source table `new_employees`. Here’s how you would use MERGE to update or insert employee records:

```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN MATCHED THEN
    UPDATE SET target.salary = source.salary
WHEN NOT MATCHED THEN
    INSERT (employee_id, name, salary) VALUES (source.employee_id, source.name, source.salary);
```

### Example 2: MERGE with Deletion
In this example, we also want to delete employees from the `employees` table that are no longer present in `new_employees`:

```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN MATCHED THEN
    UPDATE SET target.salary = source.salary
WHEN NOT MATCHED THEN
    INSERT (employee_id, name, salary) VALUES (source.employee_id, source.name, source.salary)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

## Explanation
### Common Pitfalls
1. **Incorrect Matching Logic**: Ensure that the ON clause accurately defines how records from the target and source tables are matched. If the condition is too broad or too narrow, you may not get the intended results.
2. **Ambiguous Result Sets**: If multiple records in the source table match a single record in the target table, it can lead to unexpected behavior. Always ensure that your source data is unique based on the criteria used in the ON clause.
3. **Transactional Integrity**: MERGE operations are transactional. If an error occurs during any part of the operation, none of the changes will be applied. Always test for errors and handle exceptions appropriately.

### Additional Notes
- MERGE is supported by various SQL databases such as SQL Server, Oracle, and PostgreSQL, but syntax may vary slightly. Always refer to the specific database documentation for details.
- It’s important to test MERGE statements in a controlled environment before deploying them in production to prevent unintentional data loss.

## One Line Summary
The SQL MERGE statement allows for efficient upsert operations by combining INSERT, UPDATE, and DELETE actions based on matching conditions between two tables.