<!--
Meta Description: # SQL 中的 ROLLBACK 命令详解 ## 概述 ROLLBACK 是 SQL 中用于撤销未提交事务的命令。它确保数据的一致性与完整性，特别是在出现错误或异常时。 ## 文档 ### 目的 在数据库管理系统中，事务是一组操作的集合，这些操作要么全部成功，要么全部失败。ROLLBACK 命令的...
Meta Keywords: rollback, sql, begin, salary, commit
-->

# SQL 中的 ROLLBACK 命令详解

## 概述
ROLLBACK 是 SQL 中用于撤销未提交事务的命令。它确保数据的一致性与完整性，特别是在出现错误或异常时。

## 文档
### 目的
在数据库管理系统中，事务是一组操作的集合，这些操作要么全部成功，要么全部失败。ROLLBACK 命令的主要目的是撤回在当前事务中所做的所有更改，以确保数据库状态保持在一个一致的状态。

### 用法
ROLLBACK 通常用于以下情境：
- 当发生错误时，需要撤销先前的操作。
- 在执行数据更新时，确保在错误发生时不会影响数据完整性。

### 语法
```sql
ROLLBACK;
```

在某些数据库系统中，ROLLBACK 可能会与事务名称一起使用，以撤销特定的事务。

## 示例
### 示例 1：基本用法
```sql
BEGIN TRANSACTION;

UPDATE employees SET salary = salary * 1.1 WHERE department = 'Sales';

-- 假设此时发现了错误
ROLLBACK;
```
在此示例中，如果在更新员工薪水的过程中发现错误，可以使用 ROLLBACK 来撤销薪水的更改。

### 示例 2：在存储过程中使用
```sql
CREATE PROCEDURE updateSalary()
BEGIN
    DECLARE EXIT HANDLER FOR SQLEXCEPTION
    BEGIN
        ROLLBACK;
    END;

    START TRANSACTION;
    UPDATE employees SET salary = salary * 1.1 WHERE department = 'HR';
    -- 其他 SQL 操作
    COMMIT;
END;
```
在存储过程中，如果发生 SQL 异常，将自动执行 ROLLBACK。

## 说明
- **常见陷阱**：在使用 ROLLBACK 时，必须确保已开始一个事务（使用 `BEGIN TRANSACTION`），否则 ROLLBACK 将不会有任何效果。
- **与 COMMIT 的对比**：ROLLBACK 与 COMMIT 是事务控制的两个关键命令。COMMIT 用于提交事务，确保所有更改永久保存，而 ROLLBACK 则用于撤回更改。
- **影响范围**：ROLLBACK 仅影响当前事务中所做的更改。它不会影响已提交的事务或其他并发事务。

## 一句话总结
ROLLBACK 命令在 SQL 中用于撤销当前事务的所有未提交更改，确保数据的一致性与完整性。