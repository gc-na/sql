<!--
Meta Description: # SQL 中的 END 關鍵字：用法與範例 ## 概述 在 SQL 語言中，“END” 是一個重要的關鍵字，通常用於結束控制流語句，如 CASE 語句、WHILE 循環和存儲過程的結束。它在 SQL 中扮演著結束語句的角色，確保代碼的結構完整。 ## 文檔 ### 目的 “END” 主要用於標示結...
Meta Keywords: end, sql, case, while, counter
-->

# SQL 中的 END 關鍵字：用法與範例

## 概述
在 SQL 語言中，“END” 是一個重要的關鍵字，通常用於結束控制流語句，如 CASE 語句、WHILE 循環和存儲過程的結束。它在 SQL 中扮演著結束語句的角色，確保代碼的結構完整。

## 文檔
### 目的
“END” 主要用於標示結束一個控制結構，使得 SQL 語句的語法結構清晰明瞭。它可用於多種場合，例如在 CASE 語句中用來結束一個條件分支，或在流程控制中結束一個循環。

### 使用方式
“END” 的使用取決於上下文，以下是一些常見的情況：

1. **CASE 語句**：
   在一個 CASE 語句中，“END” 標示著條件的結束。
   ```sql
   SELECT 
       CASE 
           WHEN condition1 THEN result1
           WHEN condition2 THEN result2
           ELSE default_result
       END AS result_column
   FROM table_name;
   ```

2. **WHILE 循環**：
   在 WHILE 循環中，“END” 用於結束循環的定義。
   ```sql
   WHILE condition
   BEGIN
       -- SQL 語句
   END
   ```

3. **存儲過程**：
   在定義存儲過程時，“END” 用於標示過程的結尾。
   ```sql
   CREATE PROCEDURE procedure_name
   AS
   BEGIN
       -- SQL 語句
   END
   ```

## 範例
### 使用 CASE 語句範例
```sql
SELECT 
    employee_name,
    CASE 
        WHEN salary > 50000 THEN '高收入'
        WHEN salary BETWEEN 30000 AND 50000 THEN '中等收入'
        ELSE '低收入'
    END AS income_level
FROM employees;
```

### 使用 WHILE 循環範例
```sql
DECLARE @counter INT = 1;
WHILE @counter <= 5
BEGIN
    PRINT @counter;
    SET @counter = @counter + 1;
END
```

### 使用存儲過程範例
```sql
CREATE PROCEDURE GetEmployeeCount
AS
BEGIN
    SELECT COUNT(*) AS TotalEmployees
    FROM employees;
END
```

## 解釋
### 常見陷阱
- 忘記在 CASE 語句中使用“END”會導致 SQL 語法錯誤。
- 在 WHILE 循環或存儲過程中，如果“END”位置不正確，可能會影響控制流的執行。
- 在多層嵌套結構中，確保每一層都有相對應的“END”是至關重要的，以避免混淆或錯誤。

## 一句總結
“END” 是 SQL 中結束控制流語句的關鍵字，確保代碼的結構完整性。