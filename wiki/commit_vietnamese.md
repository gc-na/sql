<!--
Meta Description: # COMMIT trong SQL: Đảm Bảo Tính Toàn Vẹn Dữ Liệu ## Tóm tắt Lệnh COMMIT trong SQL được sử dụng để xác nhận các thay đổi đối với cơ sở dữ liệu, đảm bả...
Meta Keywords: commit, trong, liệu, thay, đổi
-->

# COMMIT trong SQL: Đảm Bảo Tính Toàn Vẹn Dữ Liệu

## Tóm tắt
Lệnh COMMIT trong SQL được sử dụng để xác nhận các thay đổi đối với cơ sở dữ liệu, đảm bảo rằng tất cả các thay đổi đã thực hiện trong phiên làm việc hiện tại được lưu lại và không thể hoàn tác.

## Tài liệu
### Mục đích
Lệnh COMMIT là một phần quan trọng trong quản lý giao dịch trong SQL. Nó cho phép người dùng xác nhận các thay đổi mà họ đã thực hiện trong một giao dịch, đảm bảo rằng những thay đổi này sẽ được lưu trữ vĩnh viễn trong cơ sở dữ liệu.

### Cách sử dụng
- **Cú pháp**: 
  ```sql
  COMMIT;
  ```
- Lệnh này thường được sử dụng sau một hoặc nhiều câu lệnh DML (Data Manipulation Language) như INSERT, UPDATE hoặc DELETE.

### Chi tiết
- Khi bạn thực hiện một giao dịch, tất cả các thay đổi sẽ được lưu trữ trong bộ nhớ tạm thời cho đến khi bạn thực hiện lệnh COMMIT.
- Nếu bạn quyết định không muốn lưu các thay đổi, bạn có thể sử dụng lệnh ROLLBACK để hoàn tác giao dịch trước khi thực hiện COMMIT.
- Việc sử dụng COMMIT đảm bảo rằng dữ liệu trong cơ sở dữ liệu luôn ở trạng thái nhất quán và chính xác.

## Ví dụ
### Ví dụ 1: Xác nhận Thêm Dữ Liệu
```sql
BEGIN TRANSACTION;
INSERT INTO sinhvien (ten, tuoi) VALUES ('Nguyen Van A', 20);
COMMIT;
```

### Ví dụ 2: Xác nhận Cập Nhật Dữ Liệu
```sql
BEGIN TRANSACTION;
UPDATE sinhvien SET tuoi = 21 WHERE ten = 'Nguyen Van A';
COMMIT;
```

### Ví dụ 3: Hoàn tác Thay đổi
```sql
BEGIN TRANSACTION;
DELETE FROM sinhvien WHERE ten = 'Nguyen Van A';
ROLLBACK; -- Không lưu thay đổi
```

## Giải thích
- **Cẩn thận với các Giao dịch Dài**: Nếu bạn giữ một giao dịch mở quá lâu, nó có thể gây ra tình trạng khóa dữ liệu, ảnh hưởng đến hiệu suất của hệ thống.
- **Sự khác biệt giữa COMMIT và ROLLBACK**: COMMIT lưu các thay đổi, trong khi ROLLBACK hoàn tác chúng. Hãy chắc chắn rằng bạn chỉ thực hiện COMMIT khi bạn đã kiểm tra kỹ lưỡng các thay đổi.
- **Tính Toàn vẹn Dữ liệu**: COMMIT giúp duy trì tính toàn vẹn dữ liệu trong hệ thống, tránh tình trạng dữ liệu không nhất quán.

## Tóm tắt một dòng
Lệnh COMMIT trong SQL xác nhận và lưu lại tất cả các thay đổi trong giao dịch, đảm bảo tính chính xác và toàn vẹn của dữ liệu.