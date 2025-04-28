<!--
Meta Description: # Câu Lệnh END trong SQL: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm Tắt Câu lệnh `END` trong SQL thường được sử dụng để kết thúc các khối lệnh như `CA...
Meta Keywords: end, lệnh, trong, dụng, sql
-->

# Câu Lệnh END trong SQL: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm Tắt
Câu lệnh `END` trong SQL thường được sử dụng để kết thúc các khối lệnh như `CASE`, `BEGIN...END` hoặc cấu trúc điều kiện trong các thủ tục và hàm. Đây là một phần quan trọng trong việc quản lý luồng điều khiển của các câu lệnh SQL.

## Tài Liệu
### Mục Đích
Câu lệnh `END` được sử dụng để đánh dấu điểm kết thúc của các khối mã trong SQL, giúp cho mã trở nên rõ ràng và có cấu trúc hơn. Nó thường được sử dụng trong các tình huống như:

- Kết thúc khối `CASE` khi sử dụng trong câu lệnh `SELECT`, `UPDATE`, hoặc `DELETE`.
- Kết thúc khối lệnh `BEGIN...END` trong các thủ tục hoặc hàm.

### Cú Pháp
Cú pháp cơ bản của câu lệnh `END` thường đi kèm với cấu trúc điều kiện hoặc quy trình. Ví dụ, trong một khối lệnh `CASE`, cú pháp có thể như sau:

```sql
CASE 
    WHEN điều_kiện THEN giá_trị_1
    WHEN điều_kiện THEN giá_trị_2
    ELSE giá_trị_mặc_định
END
```

Trong một thủ tục hoặc hàm, cú pháp có thể như sau:

```sql
BEGIN
    -- Các lệnh SQL ở đây
END
```

## Ví Dụ
### Ví Dụ 1: Sử Dụng `END` trong câu lệnh `CASE`

```sql
SELECT 
    tên,
    CASE 
        WHEN điểm >= 90 THEN 'Giỏi'
        WHEN điểm >= 75 THEN 'Khá'
        ELSE 'Trung Bình'
    END AS xếp_loại
FROM học_sinh;
```

### Ví Dụ 2: Sử Dụng `END` trong thủ tục

```sql
CREATE PROCEDURE TinhTong(@a INT, @b INT)
BEGIN
    DECLARE @tong INT;
    SET @tong = @a + @b;
    SELECT @tong AS Tổng;
END;
```

## Giải Thích
### Cách Sử Dụng Đúng
- Đảm bảo rằng bạn luôn sử dụng `END` để kết thúc các khối lệnh, nếu không mã của bạn có thể bị lỗi cú pháp.
- Trong trường hợp sử dụng `CASE`, hãy chắc chắn rằng mọi điều kiện đều được kiểm tra và `END` phải theo sau cùng.

### Những Lỗi Thường Gặp
- Quên không sử dụng `END` sau khối `CASE`, dẫn đến lỗi cú pháp.
- Sử dụng nhiều khối `BEGIN` mà không có `END` tương ứng, gây ra lỗi khi thực thi thủ tục hoặc hàm.

## Tóm Tắt Một Dòng
Câu lệnh `END` trong SQL là một thành phần cần thiết để kết thúc các khối lệnh, đảm bảo mã lệnh có cấu trúc và dễ bảo trì.