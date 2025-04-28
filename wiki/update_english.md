<!--
Meta Description: # SQL UPDATE Command: Modify Existing Records in Your Database ## Synopsis The SQL UPDATE command is used to modify existing records in a database tab...
Meta Keywords: update, data, sql, set, where
-->

# SQL UPDATE Command: Modify Existing Records in Your Database

## Synopsis
The SQL UPDATE command is used to modify existing records in a database table, allowing users to change one or more fields based on specified conditions.

## Documentation

### Purpose
The UPDATE statement is an essential part of SQL that enables users to update data in a table. It is particularly useful for maintaining accurate and current records within a database.

### Usage
The basic syntax of the UPDATE command is as follows:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

- **table_name**: The name of the table containing the records you want to update.
- **SET**: Specifies the columns to be updated along with their new values.
- **WHERE**: A condition that identifies which rows to update. If omitted, all rows in the table will be updated.

### Details
1. **Multiple Columns**: You can update multiple columns simultaneously by separating them with commas in the SET clause.
2. **Conditional Updates**: Always include a WHERE clause to avoid updating all records unintentionally.
3. **Data Types**: Ensure that the values assigned in the SET clause match the data types of the respective columns.
4. **Transactions**: Consider using transactions to maintain data integrity, especially when performing multiple updates.

## Examples

**Example 1: Update a Single Column**
```sql
UPDATE employees
SET salary = 60000
WHERE employee_id = 101;
```
This updates the salary of the employee with ID 101 to 60000.

**Example 2: Update Multiple Columns**
```sql
UPDATE products
SET price = 19.99, stock = 50
WHERE product_id = 202;
```
This updates the price and stock of the product with ID 202.

**Example 3: Update with a Condition**
```sql
UPDATE orders
SET status = 'Shipped'
WHERE order_date < '2023-01-01' AND status = 'Pending';
```
This updates the status of all pending orders placed before January 1, 2023, to 'Shipped'.

## Explanation

### Common Pitfalls
- **Omitting WHERE Clause**: Without a WHERE clause, every record in the table will be updated, which could lead to data loss or corruption.
- **Incorrect Data Types**: Assigning a value that does not match the column type can cause errors or unexpected behavior.
- **Transactions**: Not using transactions for critical updates can result in inconsistent data if an error occurs during the update process.

### Gotchas
- **Null Values**: If a column is set to NULL, it may lead to loss of data. Always check if NULL is a valid value for that column.
- **Default Values**: Be aware of default values that may be reset when updating a row.
- **Triggers**: If there are any triggers associated with the table, they may execute during the update, potentially causing unintended side effects.

## One Line Summary
The SQL UPDATE command allows users to change existing records in a database table based on specified conditions, ensuring data accuracy and relevance.