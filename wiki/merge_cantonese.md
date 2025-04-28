<!--
Meta Description: # SQL MERGE 指令：高效的數據合併解決方案 ## 概要 SQL MERGE 指令是一個強大的 SQL 語句，用於同時插入、更新或刪除資料，根據源資料與目標資料的匹配情況進行操作。這使得數據同步和維護更加高效。 ## 文件說明 ### 目的 SQL MERGE 主要用於在數據庫中根據某些條件...
Meta Keywords: merge, source, when, matched, sql
-->

# SQL MERGE 指令：高效的數據合併解決方案

## 概要
SQL MERGE 指令是一個強大的 SQL 語句，用於同時插入、更新或刪除資料，根據源資料與目標資料的匹配情況進行操作。這使得數據同步和維護更加高效。

## 文件說明
### 目的
SQL MERGE 主要用於在數據庫中根據某些條件合併數據。它能夠在一個操作中進行插入、更新或刪除，從而減少了多次訪問數據庫的需求，提高了性能。

### 使用方法
MERGE 語法結構如下：
```sql
MERGE INTO target_table AS target
USING source_table AS source
ON target.key_column = source.key_column
WHEN MATCHED THEN
    UPDATE SET target.column1 = source.column1, target.column2 = source.column2
WHEN NOT MATCHED THEN
    INSERT (column1, column2) VALUES (source.column1, source.column2)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```
- `target_table` 是要合併的目標表。
- `source_table` 是提供更新或插入數據的源表。
- `ON` 子句定義了匹配的條件。
- `WHEN MATCHED` 指定了當找到匹配時的操作。
- `WHEN NOT MATCHED` 指定了當沒有找到匹配時的插入操作。
- `WHEN NOT MATCHED BY SOURCE` 指定了當目標表中的記錄在源表中不存在時的刪除操作。

### 詳細說明
在使用 SQL MERGE 時，必須確保正確設置匹配條件，以避免意外刪除或更新數據。此外，不同的數據庫管理系統（DBMS）可能在語法和功能上有些許差異，因此建議查閱具體系統的文檔。

## 範例
### 基本範例
假設我們有一個名為 `employees` 的目標表和一個名為 `new_employees` 的源表，我們可以這樣使用 MERGE：
```sql
MERGE INTO employees AS e
USING new_employees AS n
ON e.employee_id = n.employee_id
WHEN MATCHED THEN
    UPDATE SET e.name = n.name, e.salary = n.salary
WHEN NOT MATCHED THEN
    INSERT (employee_id, name, salary) VALUES (n.employee_id, n.name, n.salary)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

## 解釋
在使用 MERGE 時，常見的 pitfalls 包括：
- **匹配條件不正確**：確保使用正確的列來進行匹配，以避免意外更新或刪除不應該影響的記錄。
- **性能問題**：在大型表上使用 MERGE 可能會導致性能下降，因此建議在執行前評估數據量。
- **數據庫兼容性**：不同的數據庫可能有不同的 MERGE 語法，應根據具體數據庫進行調整。

## 一句總結
SQL MERGE 指令是一個高效的數據合併工具，能在一次操作中根據匹配情況進行插入、更新或刪除。