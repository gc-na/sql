<!--
Meta Description: # SQL UPDATE 指令：更新資料的完整指南 ## 概述 SQL 中的 UPDATE 指令用於修改資料表中已有的記錄。透過此指令，使用者可以有效更新特定行的數據，以滿足數據處理及管理的需求。 ## 文件說明 UPDATE 指令的主要目的是讓使用者能夠對資料表中的一或多行資料進行修改。此指令的基...
Meta Keywords: update, where, sql, set, inactive
-->

# SQL UPDATE 指令：更新資料的完整指南

## 概述
SQL 中的 UPDATE 指令用於修改資料表中已有的記錄。透過此指令，使用者可以有效更新特定行的數據，以滿足數據處理及管理的需求。

## 文件說明
UPDATE 指令的主要目的是讓使用者能夠對資料表中的一或多行資料進行修改。此指令的基本語法如下：

```sql
UPDATE 表名
SET 列名1 = 新值1, 列名2 = 新值2, ...
WHERE 條件;
```

- **表名**：要更新的資料表名稱。
- **SET**：指定要更新的列及其新值。
- **WHERE**：可選參數，用於限制要更新的行。如果不使用 WHERE，則所有行都會被更新。

### 使用方法
1. 確認需要更新的資料表及其結構。
2. 使用 UPDATE 指令指定更新的列與新值。
3. 根據需要使用 WHERE 條件以限制更新的範圍。

## 範例
以下是幾個基本的更新範例：

### 更新單一列
```sql
UPDATE Customers
SET ContactName = '新聯絡人'
WHERE CustomerID = 1;
```

### 更新多個列
```sql
UPDATE Products
SET Price = 20.99, Stock = 100
WHERE ProductID = 5;
```

### 更新所有行
```sql
UPDATE Employees
SET Status = 'Inactive';
```
> 注意：上述範例會將所有員工的狀態更新為 'Inactive'。

## 解釋
在使用 UPDATE 指令時，使用者需要特別注意以下幾點：

- **WHERE 條件的重要性**：未使用 WHERE 的 UPDATE 指令將影響整個資料表，這可能導致意外數據損失。
- **數據類型匹配**：在更新時，必須確保新值的數據類型與目標列的數據類型相符，否則將會發生錯誤。
- **事務管理**：對於批量更新，建議使用事務來確保數據一致性，如使用 BEGIN TRANSACTION 和 COMMIT。

## 一句總結
SQL 的 UPDATE 指令允許使用者高效地修改資料表中現有的記錄，是數據管理的重要工具。