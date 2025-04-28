<!--
Meta Description: # Lệnh INSERT trong SQL: Cách Thêm Dữ Liệu vào Cơ Sở Dữ Liệu ## Tóm tắt Lệnh INSERT trong SQL được sử dụng để thêm một hoặc nhiều bản ghi mới vào bảng...
Meta Keywords: trong, liệu, insert, thêm, sql
-->

# Lệnh INSERT trong SQL: Cách Thêm Dữ Liệu vào Cơ Sở Dữ Liệu

## Tóm tắt
Lệnh INSERT trong SQL được sử dụng để thêm một hoặc nhiều bản ghi mới vào bảng trong cơ sở dữ liệu. Đây là một trong những lệnh cơ bản và thường xuyên được sử dụng trong các thao tác quản lý dữ liệu.

## Tài liệu

### Mục đích
Lệnh INSERT cho phép người dùng thêm dữ liệu vào các bảng trong cơ sở dữ liệu SQL. Điều này rất quan trọng trong việc xây dựng và duy trì dữ liệu, đặc biệt trong các ứng dụng yêu cầu cập nhật thông tin thường xuyên.

### Cách sử dụng
Cú pháp cơ bản của lệnh INSERT như sau:

```sql
INSERT INTO tên_bảng (cột1, cột2, cột3, ...)
VALUES (giá_trị1, giá_trị2, giá_trị3, ...);
```

Trong đó:
- `tên_bảng`: Tên của bảng mà bạn muốn thêm dữ liệu.
- `cột1, cột2, cột3, ...`: Danh sách các cột trong bảng mà bạn muốn thêm giá trị.
- `giá_trị1, giá_trị2, giá_trị3, ...`: Các giá trị tương ứng với các cột đã chỉ định.

### Chi tiết
- Bạn có thể sử dụng lệnh INSERT để thêm một bản ghi hoặc nhiều bản ghi cùng một lúc.
- Nếu bạn không chỉ định danh sách cột, bạn phải cung cấp giá trị cho tất cả các cột trong bảng theo thứ tự mà chúng được định nghĩa.

## Ví dụ

### Ví dụ 1: Thêm một bản ghi
```sql
INSERT INTO sinh_vien (ho_ten, tuoi, dia_chi)
VALUES ('Nguyen Van A', 20, 'Ha Noi');
```

### Ví dụ 2: Thêm nhiều bản ghi
```sql
INSERT INTO sinh_vien (ho_ten, tuoi, dia_chi)
VALUES 
('Nguyen Van B', 22, 'Da Nang'),
('Tran Thi C', 19, 'Ho Chi Minh');
```

### Ví dụ 3: Thêm bản ghi mà không chỉ định cột
```sql
INSERT INTO sinh_vien
VALUES (NULL, 'Le Thi D', 21, 'Hai Phong');
```

## Giải thích
- **Lỗi trùng khóa chính**: Khi thêm dữ liệu, nếu giá trị của khóa chính đã tồn tại trong bảng, SQL sẽ trả về lỗi. Hãy chắc chắn rằng giá trị của khóa chính là duy nhất.
- **Kiểu dữ liệu không hợp lệ**: Đảm bảo rằng các giá trị được chèn vào bảng có kiểu dữ liệu phù hợp với định nghĩa của các cột trong bảng.
- **Giá trị NULL**: Nếu một cột không cho phép giá trị NULL, bạn cần phải cung cấp giá trị hợp lệ cho cột đó khi thực hiện lệnh INSERT.

## Tóm tắt một dòng
Lệnh INSERT trong SQL cho phép người dùng thêm dữ liệu mới vào bảng trong cơ sở dữ liệu một cách hiệu quả và linh hoạt.