<!--
Meta Description: # SQL TRUNCATE 命令：快速清空資料表的最佳選擇 ## 概述 TRUNCATE 是 SQL 中一個用於快速清除資料表中所有資料的命令。相較於 DELETE 命令，TRUNCATE 更有效率，因為它不會逐行刪除，而是重置整個資料表。 ## 文件說明 TRUNCATE 命令的主要目的是高效地...
Meta Keywords: truncate, sql, delete, table, table_name
-->

# SQL TRUNCATE 命令：快速清空資料表的最佳選擇

## 概述
TRUNCATE 是 SQL 中一個用於快速清除資料表中所有資料的命令。相較於 DELETE 命令，TRUNCATE 更有效率，因為它不會逐行刪除，而是重置整個資料表。

## 文件說明
TRUNCATE 命令的主要目的是高效地刪除資料表中的所有記錄。與 DELETE 命令相比，TRUNCATE 的速度更快，因為它不會記錄每一行的刪除操作，並且通常不會觸發觸發器（Triggers）。此命令通常在需要重置資料表時使用，特別是在測試或開發階段。

### 用法
TRUNCATE 命令的基本語法如下：

```sql
TRUNCATE TABLE table_name;
```

- `table_name`：指定要清空的資料表名稱。

### 注意事項
1. TRUNCATE 命令無法針對有外鍵約束的資料表執行，除非先刪除約束。
2. TRUNCATE 將無法恢復，執行後資料將永久消失。
3. 執行 TRUNCATE 命令不會觸發 DELETE 觸發器。
4. TRUNCATE 將重置資料表的自增計數器（如果有）。

## 範例
以下為 TRUNCATE 命令的基本使用範例：

### 範例 1：清空資料表
```sql
TRUNCATE TABLE employees;
```
此命令將清空 `employees` 資料表中的所有資料。

### 範例 2：使用 TRUNCATE 清空產品資料表
```sql
TRUNCATE TABLE products;
```
這將移除 `products` 資料表中的所有記錄，並重置自增計數器。

## 解釋
使用 TRUNCATE 命令時需注意以下幾點：

- **無法恢復**：因為 TRUNCATE 不會記錄逐行刪除，所以一旦執行便無法恢復資料。
- **外鍵約束**：若資料表與其他資料表存在外鍵關聯，必須先刪除外鍵約束才能進行 TRUNCATE 操作。
- **性能考量**：TRUNCATE 通常比 DELETE 快，特別是在處理大量資料時，因為它不需要掃描每一行。
  
## 總結
TRUNCATE 是一個高效的 SQL 命令，用於快速清空資料表中的所有資料，並重置自增計數器，是在清除資料時的理想選擇。