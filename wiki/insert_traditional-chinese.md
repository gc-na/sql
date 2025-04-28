<!--
Meta Description: # SQL INSERT 指令：數據庫中插入數據的基礎 ## 概述 SQL 的 INSERT 指令用於將新記錄添加到數據庫表中。這是數據操作語言（DML）的一部分，對於數據庫的更新和維護至關重要。 ## 文檔 ### 目的 INSERT 指令的主要目的是在數據庫的表中插入新數據行。無論是用於添加用戶...
Meta Keywords: insert, sql, into, values, select
-->

# SQL INSERT 指令：數據庫中插入數據的基礎

## 概述
SQL 的 INSERT 指令用於將新記錄添加到數據庫表中。這是數據操作語言（DML）的一部分，對於數據庫的更新和維護至關重要。

## 文檔
### 目的
INSERT 指令的主要目的是在數據庫的表中插入新數據行。無論是用於添加用戶信息、產品資料還是其他類型的數據，INSERT 都是數據庫操作的基本功能之一。

### 用法
INSERT 指令的基本語法如下：

```sql
INSERT INTO 表名 (欄位1, 欄位2, ..., 欄位N)
VALUES (值1, 值2, ..., 值N);
```

- **表名**：要插入數據的目標表。
- **欄位**：需要插入數據的列名。
- **值**：對應欄位的數據值。

當插入的數據行中包含所有欄位的數據時，可以省略欄位名稱：

```sql
INSERT INTO 表名
VALUES (值1, 值2, ..., 值N);
```

### 詳細信息
- **多行插入**：一次可以插入多條記錄，語法如下：

```sql
INSERT INTO 表名 (欄位1, 欄位2)
VALUES (值1, 值2),
       (值3, 值4),
       (值5, 值6);
```

- **使用 SELECT**：可以通過選擇其他表的數據來插入數據：

```sql
INSERT INTO 目標表 (欄位1, 欄位2)
SELECT 欄位A, 欄位B FROM 來源表;
```

- **自動生成的欄位**：如果表中有自動增長的欄位，可以在插入時省略該欄位。

## 示例
### 基本插入示例
插入一條用戶數據：

```sql
INSERT INTO Users (username, email)
VALUES ('john_doe', 'john@example.com');
```

### 多行插入示例
插入多條產品數據：

```sql
INSERT INTO Products (product_name, price)
VALUES ('Laptop', 999.99),
       ('Smartphone', 499.99);
```

### 使用 SELECT 插入示例
從一個表中插入數據到另一個表：

```sql
INSERT INTO ArchivedOrders (order_id, order_date)
SELECT order_id, order_date FROM Orders WHERE order_date < '2023-01-01';
```

## 解釋
- **常見陷阱**：確保插入的數據類型與表的欄位類型匹配。若不匹配，將導致錯誤。
- **唯一性約束**：如果某個欄位有唯一性約束，插入重複值會導致錯誤。
- **NULL 值**：對於可以接受 NULL 的欄位，可以在插入時省略該欄位或明確插入 NULL。

## 一句總結
SQL 的 INSERT 指令用於將新數據行添加到數據庫表，是數據庫操作的基本組成部分。