<!--
Meta Description: # Khai báo biến trong SQL: Cú pháp và Cách sử dụng ## Tóm tắt Lệnh `DECLARE` trong SQL được sử dụng để khai báo các biến cục bộ trong các khối mã, cho...
Meta Keywords: biến, trong, sql, lệnh, declare
-->

# Khai báo biến trong SQL: Cú pháp và Cách sử dụng

## Tóm tắt
Lệnh `DECLARE` trong SQL được sử dụng để khai báo các biến cục bộ trong các khối mã, cho phép người dùng lưu trữ và thao tác với dữ liệu tạm thời trong quá trình thực hiện các câu lệnh SQL.

## Tài liệu
Lệnh `DECLARE` là một phần quan trọng trong ngôn ngữ lập trình SQL, đặc biệt trong các hệ quản trị cơ sở dữ liệu như SQL Server, PostgreSQL và MySQL. Mục đích chính của lệnh này là khai báo biến, giúp người dùng lưu trữ dữ liệu tạm thời trong phiên làm việc hiện tại.

### Cú pháp
Cú pháp cơ bản để sử dụng lệnh `DECLARE` là:

```sql
DECLARE @variable_name datatype;
```

- `@variable_name`: Tên của biến bạn muốn khai báo, thường bắt đầu bằng ký tự `@` trong SQL Server.
- `datatype`: Kiểu dữ liệu của biến, ví dụ như `INT`, `VARCHAR`, `DATETIME`, v.v.

### Mục đích
Lệnh `DECLARE` cho phép người dùng:
- Khai báo biến cục bộ để sử dụng trong các câu lệnh SQL.
- Thực hiện các phép toán và lưu trữ kết quả vào biến.
- Tăng cường khả năng lập trình trong SQL với các khối mã, vòng lặp và điều kiện.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về việc sử dụng lệnh `DECLARE`:

### Ví dụ 1: Khai báo biến số nguyên
```sql
DECLARE @count INT;
SET @count = 10;
SELECT @count AS 'Giá trị của biến count';
```

### Ví dụ 2: Khai báo biến chuỗi
```sql
DECLARE @name VARCHAR(50);
SET @name = 'Nguyễn Văn A';
SELECT @name AS 'Tên người dùng';
```

### Ví dụ 3: Sử dụng biến trong câu lệnh SQL
```sql
DECLARE @totalPrice DECIMAL(10, 2);
SET @totalPrice = (SELECT SUM(price) FROM Products);
SELECT @totalPrice AS 'Tổng giá';
```

## Giải thích
Mặc dù lệnh `DECLARE` là một công cụ mạnh mẽ, người dùng cần lưu ý một số vấn đề sau:
- Biến được khai báo chỉ tồn tại trong phạm vi của khối mã mà nó được tạo ra. Nếu bạn cố gắng truy cập biến ngoài phạm vi đó, bạn sẽ gặp lỗi.
- Kiểu dữ liệu của biến cần được xác định chính xác. Việc sử dụng sai kiểu dữ liệu có thể dẫn đến lỗi trong quá trình thực thi.
- Không phải tất cả các hệ quản trị cơ sở dữ liệu đều hỗ trợ cú pháp giống nhau, vì vậy cần tham khảo tài liệu cụ thể cho từng hệ thống.

## Tóm tắt một dòng
Lệnh `DECLARE` trong SQL cho phép người dùng khai báo và sử dụng các biến cục bộ trong các khối mã để lưu trữ và thao tác với dữ liệu tạm thời.