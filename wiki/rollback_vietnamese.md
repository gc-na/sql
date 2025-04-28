<!--
Meta Description: # ROLLBACK trong SQL: Khôi phục Giao dịch và Quản lý Dữ liệu ## Tóm tắt ROLLBACK là một lệnh trong SQL được sử dụng để hoàn tác các thay đổi đã thực h...
Meta Keywords: rollback, trong, các, giao, dịch
-->

# ROLLBACK trong SQL: Khôi phục Giao dịch và Quản lý Dữ liệu

## Tóm tắt
ROLLBACK là một lệnh trong SQL được sử dụng để hoàn tác các thay đổi đã thực hiện trong một giao dịch. Lệnh này rất hữu ích khi bạn muốn đảm bảo rằng các thao tác trên cơ sở dữ liệu không làm hỏng dữ liệu trong trường hợp xảy ra lỗi hoặc khi bạn quyết định không thực hiện các thay đổi.

## Tài liệu hướng dẫn
### Mục đích
Lệnh ROLLBACK cho phép người dùng quay lại trạng thái trước đó của cơ sở dữ liệu bằng cách hủy bỏ tất cả các thay đổi được thực hiện trong giao dịch hiện tại. Điều này rất quan trọng trong các ứng dụng yêu cầu tính toàn vẹn dữ liệu cao, chẳng hạn như trong tài chính.

### Cách sử dụng
Để sử dụng lệnh ROLLBACK, trước tiên bạn cần bắt đầu một giao dịch bằng lệnh `BEGIN TRANSACTION`. Sau đó, bạn có thể thực hiện một hoặc nhiều thao tác SQL như `INSERT`, `UPDATE`, hoặc `DELETE`. Nếu bạn quyết định không muốn giữ lại các thay đổi, bạn chỉ cần gọi lệnh ROLLBACK.

#### Cú pháp:
```sql
BEGIN TRANSACTION;
-- Các lệnh SQL như INSERT, UPDATE, DELETE
ROLLBACK;
```

### Chi tiết
- **Giao dịch**: ROLLBACK chỉ hoạt động trong bối cảnh của một giao dịch. Nếu không có giao dịch nào đang diễn ra, lệnh này sẽ không có tác dụng.
- **Tính toàn vẹn dữ liệu**: Sử dụng ROLLBACK giúp bảo vệ tính toàn vẹn của dữ liệu, ngăn chặn việc lưu trữ các thay đổi không mong muốn.
- **Kết hợp với COMMIT**: Trong khi ROLLBACK hoàn tác tất cả các thay đổi, lệnh `COMMIT` sẽ xác nhận các thay đổi và lưu chúng vào cơ sở dữ liệu.

## Ví dụ
### Ví dụ 1: Hoàn tác thay đổi
```sql
BEGIN TRANSACTION;
INSERT INTO KhachHang (Ten, DiaChi) VALUES ('Nguyen Van A', 'Ha Noi');
ROLLBACK;
```
Trong ví dụ này, khách hàng 'Nguyen Van A' sẽ không được thêm vào bảng `KhachHang` vì lệnh ROLLBACK được thực hiện.

### Ví dụ 2: Sử dụng ROLLBACK sau khi có lỗi
```sql
BEGIN TRANSACTION;
UPDATE SanPham SET Gia = Gia * 1.1 WHERE MaSP = 'SP001';
-- Giả sử có lỗi ở đây
ROLLBACK;
```
Nếu có lỗi trong quá trình thực hiện, tất cả các thay đổi sẽ được hoàn tác.

## Giải thích
### Những cạm bẫy phổ biến
- **Không có giao dịch**: Nếu bạn gọi ROLLBACK mà không có giao dịch nào đang mở, bạn sẽ nhận được thông báo lỗi.
- **Giao dịch không được xác nhận**: Nếu bạn quên gọi lệnh COMMIT sau khi thực hiện các thay đổi, và sau đó gọi ROLLBACK, tất cả sẽ bị hủy bỏ, bao gồm cả những thay đổi mà bạn có thể muốn giữ lại.
- **Khó khăn trong việc theo dõi**: Trong các hệ thống lớn, việc theo dõi giao dịch và sử dụng ROLLBACK có thể trở nên phức tạp, dẫn đến việc mất dữ liệu không mong muốn.

## Tóm tắt một dòng
Lệnh ROLLBACK trong SQL cho phép người dùng hoàn tác các thay đổi không mong muốn trong giao dịch, đảm bảo tính toàn vẹn dữ liệu.