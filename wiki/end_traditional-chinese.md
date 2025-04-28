<!--
Meta Description: # SQL中的END命令詳解 ## 概述 在SQL中，`END`是一個重要的命令，常用於結束控制結構，例如`CASE`、`IF...ELSE`和儲存過程。它的主要功能是標記邏輯結構的結尾，以便正確執行SQL語句。 ## 文檔說明 ### 目的 `END`命令的主要目的是提供一個結束標記，讓SQL解釋...
Meta Keywords: end, case, else, counter, sql
-->

# SQL中的END命令詳解

## 概述
在SQL中，`END`是一個重要的命令，常用於結束控制結構，例如`CASE`、`IF...ELSE`和儲存過程。它的主要功能是標記邏輯結構的結尾，以便正確執行SQL語句。

## 文檔說明
### 目的
`END`命令的主要目的是提供一個結束標記，讓SQL解釋器知道何時停止執行特定的控制結構。這在複雜的查詢或程序中尤為重要，因為它幫助維護語句的清晰性和結構。

### 使用方式
`END`通常與以下控制結構一起使用：

1. **CASE**: 用於條件表達式的結束。
2. **IF...ELSE**: 用於條件語句的結束。
3. **WHILE**: 在迴圈結束時使用，確保迴圈的正確終止。

### 詳細說明
在SQL中，`END`的使用經常與其他語句結合，以形成完整的邏輯結構。每當使用`CASE`或`IF`時，必須使用`END`來指示結構的結尾，這樣SQL解釋器才能正確解析並執行語句。

## 範例
以下是`END`命令的基本用法示例：

### 範例1：使用CASE結構
```sql
SELECT 
    StudentName,
    CASE 
        WHEN Score >= 90 THEN '優'
        WHEN Score >= 80 THEN '良'
        ELSE '及格'
    END AS Grade
FROM Students;
```

### 範例2：使用IF...ELSE結構
```sql
IF (SELECT COUNT(*) FROM Employees) > 100
BEGIN
    PRINT '員工數量超過100人';
END
ELSE
BEGIN
    PRINT '員工數量低於或等於100人';
END
```

### 範例3：使用WHILE循環
```sql
DECLARE @Counter INT = 0;
WHILE @Counter < 5
BEGIN
    PRINT @Counter;
    SET @Counter = @Counter + 1;
END
```

## 解釋
在使用`END`時，有幾個常見的陷阱需要注意：

1. **缺少END**：在複雜的條件語句中，如果忘記添加`END`，將會導致語法錯誤。
2. **多重結構**：當有多個嵌套的`IF...ELSE`或`CASE`時，必須確保所有的`END`都正確對應，以避免混淆。
3. **SQL版本差異**：不同版本的SQL可能對`END`的使用有細微差異，建議查閱相應版本的文檔以獲取準確信息。

## 一句總結
`END`命令在SQL中用於結束控制結構，確保語句的清晰與正確執行。