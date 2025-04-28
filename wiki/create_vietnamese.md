<!--
Meta Description: # Lệnh CREATE trong SQL: Tạo Bảng và Đối Tượng Cơ Sở Dữ Liệu ## Tóm tắt Lệnh CREATE trong SQL được sử dụng để tạo các đối tượng cơ sở dữ liệu như bảng...
Meta Keywords: liệu, tạo, bảng, create, sql
-->

# Lệnh CREATE trong SQL: Tạo Bảng và Đối Tượng Cơ Sở Dữ Liệu

## Tóm tắt
Lệnh CREATE trong SQL được sử dụng để tạo các đối tượng cơ sở dữ liệu như bảng, chỉ mục, và chế độ xem. Đây là một trong những lệnh cơ bản nhất trong SQL, cho phép người dùng định nghĩa cấu trúc dữ liệu ban đầu cho một cơ sở dữ liệu.

## Tài liệu
### Mục đích
Lệnh CREATE cho phép người dùng xây dựng các thành phần cơ bản của một cơ sở dữ liệu, bao gồm định nghĩa bảng, cột, kiểu dữ liệu và các ràng buộc.

### Cú pháp
Cú pháp cơ bản của lệnh CREATE cho bảng như sau:
```sql
CREATE TABLE ten_bang (
    ten_cot1 kieu_du_lieu [ràng_buộc],
    ten_cot2 kieu_du_lieu [ràng_buộc],
    ...
);
```

### Sử dụng
- **Tạo bảng:** Sử dụng lệnh CREATE TABLE để tạo một bảng mới trong cơ sở dữ liệu.
- **Tạo chỉ mục:** Sử dụng lệnh CREATE INDEX để tạo chỉ mục giúp tăng tốc độ truy vấn.
- **Tạo chế độ xem:** Sử dụng lệnh CREATE VIEW để tạo chế độ xem ảo từ một hoặc nhiều bảng.

### Ví dụ
- Tạo bảng đơn giản:
```sql
CREATE TABLE KhachHang (
    ID INT PRIMARY KEY,
    Ten NVARCHAR(100),
    DiaChi NVARCHAR(255)
);
```

- Tạo bảng với ràng buộc:
```sql
CREATE TABLE SanPham (
    ID INT PRIMARY KEY,
    Ten NVARCHAR(100) NOT NULL,
    Gia DECIMAL(10, 2) CHECK (Gia > 0)
);
```

- Tạo chỉ mục:
```sql
CREATE INDEX idx_ten ON KhachHang (Ten);
```

- Tạo chế độ xem:
```sql
CREATE VIEW KhachHangView AS
SELECT Ten, DiaChi FROM KhachHang;
```

## Giải thích
### Những cạm bẫy thường gặp
- **Thiếu ràng buộc:** Khi tạo bảng, việc không định nghĩa ràng buộc như PRIMARY KEY, FOREIGN KEY có thể dẫn đến dữ liệu không nhất quán.
- **Kiểu dữ liệu không chính xác:** Đảm bảo rằng kiểu dữ liệu được chọn phù hợp với dữ liệu mà bạn dự kiến lưu trữ.
- **Tên trùng lặp:** Kiểm tra xem tên bảng hoặc chỉ mục có bị trùng với tên đã tồn tại trong cơ sở dữ liệu hay không.

### Lưu ý bổ sung
- Hãy chắc chắn rằng bạn có quyền tạo bảng trong cơ sở dữ liệu mà bạn đang làm việc.
- Sử dụng các công cụ quản lý cơ sở dữ liệu có giao diện đồ họa để dễ dàng tạo bảng mà không cần viết SQL.

## Tóm tắt một dòng
Lệnh CREATE trong SQL cho phép người dùng tạo các đối tượng cơ sở dữ liệu như bảng, chỉ mục và chế độ xem để tổ chức và quản lý dữ liệu hiệu quả.