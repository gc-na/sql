<!--
Meta Description: # SQL SELECT 語句：查詢數據的基礎 ## 概述 SELECT 語句是 SQL（結構化查詢語言）中最重要的命令之一，用於從數據庫中檢索數據。通過使用 SELECT 語句，使用者可以選擇特定的列，過濾數據，並以不同的方式展示結果。 ## 文檔 ### 目的 SELECT 語句的主要目的是從數...
Meta Keywords: select, sql, from, table_name, where
-->

# SQL SELECT 語句：查詢數據的基礎

## 概述
SELECT 語句是 SQL（結構化查詢語言）中最重要的命令之一，用於從數據庫中檢索數據。通過使用 SELECT 語句，使用者可以選擇特定的列，過濾數據，並以不同的方式展示結果。

## 文檔
### 目的
SELECT 語句的主要目的是從數據庫中的表中提取數據。它允許使用者定義想要查詢的列，並可以根據需要進行排序和過濾。

### 用法
基本語法如下：
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
- **column1, column2, ...**：需要檢索的列名。
- **table_name**：數據來源的表名。
- **condition**：用於過濾結果的條件（可選）。

### 詳細信息
- SELECT 語句可以與多種其他 SQL 句子結合使用，例如 JOIN、GROUP BY 和 ORDER BY，來完成更複雜的查詢。
- 使用星號（*）可以選擇所有列：
  ```sql
  SELECT * FROM table_name;
  ```
- 可以使用 DISTINCT 關鍵字來獲取唯一值：
  ```sql
  SELECT DISTINCT column1 FROM table_name;
  ```

## 示例
1. 基本查詢：
   ```sql
   SELECT first_name, last_name FROM employees;
   ```

2. 使用 WHERE 子句過濾結果：
   ```sql
   SELECT * FROM employees WHERE department = 'Sales';
   ```

3. 排序查詢結果：
   ```sql
   SELECT first_name, last_name FROM employees ORDER BY last_name ASC;
   ```

4. 獲取唯一值：
   ```sql
   SELECT DISTINCT job_title FROM employees;
   ```

## 解釋
- **常見陷阱**：
  - 忽略 WHERE 子句可能導致返回過多的數據。
  - 使用不正確的列名會導致查詢失敗。
  - 忽略 SQL 注入風險，特別是在處理用戶輸入時。

- **額外注意**：
  - 確保使用者擁有訪問指定表的權限。
  - 對於大型數據集，使用 LIMIT 子句可以提高查詢效率。

## 一行總結
SELECT 語句是 SQL 中用來從數據庫表中檢索數據的基本工具。