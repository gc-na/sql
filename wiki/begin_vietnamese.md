<!--
Meta Description: # Lệnh BEGIN trong SQL: Cách Sử Dụng và Ví Dụ ## Tóm tắt Lệnh `BEGIN` trong SQL được sử dụng để bắt đầu một giao dịch (transaction). Nó cho phép người...
Meta Keywords: lệnh, begin, sql, giao, dịch
-->

# Lệnh BEGIN trong SQL: Cách Sử Dụng và Ví Dụ

## Tóm tắt
Lệnh `BEGIN` trong SQL được sử dụng để bắt đầu một giao dịch (transaction). Nó cho phép người dùng nhóm nhiều lệnh SQL lại với nhau, đảm bảo rằng tất cả các lệnh đó sẽ được thực thi thành công hoặc không có lệnh nào được thực hiện.

## Tài liệu
Lệnh `BEGIN` là một phần quan trọng trong quản lý giao dịch trong SQL. Giao dịch là một chuỗi các thao tác mà bạn muốn thực hiện cùng nhau. Nếu một trong số các thao tác thất bại, toàn bộ giao dịch sẽ bị hủy bỏ, đảm bảo tính toàn vẹn của dữ liệu. 

### Mục đích
Mục đích chính của lệnh `BEGIN` là để bắt đầu một giao dịch. Điều này rất hữu ích khi bạn cần thực hiện nhiều thao tác trong cơ sở dữ liệu mà bạn muốn đảm bảo rằng chúng thành công hoặc không có thao tác nào được thực hiện.

### Cách Sử Dụng
Cú pháp cơ bản của lệnh `BEGIN` rất đơn giản:

```sql
BEGIN;
-- Các lệnh SQL khác
COMMIT; -- Hoặc ROLLBACK;
```

Khi một giao dịch bắt đầu với lệnh `BEGIN`, bạn có thể thực hiện nhiều thao tác như `INSERT`, `UPDATE`, hoặc `DELETE`. Nếu mọi thao tác đều thành công, bạn sẽ kết thúc giao dịch bằng cách sử dụng lệnh `COMMIT`. Ngược lại, nếu có lỗi xảy ra, bạn có thể sử dụng lệnh `ROLLBACK` để hủy bỏ tất cả các thao tác đã thực hiện trong giao dịch đó.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng lệnh `BEGIN` trong SQL:

### Ví dụ 1: Thêm Dữ Liệu
```sql
BEGIN;
INSERT INTO khach_hang (ten, dia_chi) VALUES ('Nguyen Van A', 'Ha Noi');
INSERT INTO don_hang (khach_hang_id, san_pham_id) VALUES (1, 2);
COMMIT;
```

### Ví dụ 2: Cập Nhật Dữ Liệu với ROLLBACK
```sql
BEGIN;
UPDATE san_pham SET gia = gia * 1.1 WHERE id = 1;
-- Giả sử có lỗi xảy ra ở đây
ROLLBACK;
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng lệnh `BEGIN`:

- **Khóa Dữ Liệu**: Khi một giao dịch bắt đầu, các bản ghi có thể bị khóa cho đến khi giao dịch được hoàn tất, điều này có thể gây ra sự chậm trễ trong các giao dịch khác.
- **Quản lý Lỗi**: Đảm bảo rằng bạn luôn sử dụng `ROLLBACK` khi có lỗi xảy ra để tránh mất dữ liệu.
- **Ngữ Cảnh Khác Nhau**: Cú pháp và chức năng của `BEGIN` có thể khác nhau giữa các hệ quản trị cơ sở dữ liệu khác nhau (như MySQL, PostgreSQL, SQL Server).

## Tóm tắt một dòng
Lệnh `BEGIN` trong SQL được sử dụng để bắt đầu một giao dịch, cho phép nhóm nhiều lệnh SQL lại với nhau, đảm bảo tính toàn vẹn của dữ liệu.