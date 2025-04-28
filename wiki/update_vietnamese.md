<!--
Meta Description: # Lệnh UPDATE trong SQL: Cập Nhật Dữ Liệu Hiệu Quả ## Tóm tắt Lệnh `UPDATE` trong SQL được sử dụng để thay đổi dữ liệu hiện có trong bảng. Đây là một ...
Meta Keywords: cập, trong, nhật, update, bản
-->

# Lệnh UPDATE trong SQL: Cập Nhật Dữ Liệu Hiệu Quả

## Tóm tắt
Lệnh `UPDATE` trong SQL được sử dụng để thay đổi dữ liệu hiện có trong bảng. Đây là một trong những lệnh cơ bản và quan trọng giúp quản lý và duy trì tính chính xác của cơ sở dữ liệu.

## Tài liệu
### Mục đích
Lệnh `UPDATE` cho phép người dùng cập nhật một hoặc nhiều bản ghi trong bảng bằng cách thay đổi giá trị của một hoặc nhiều cột.

### Cú pháp
Cú pháp cơ bản của lệnh `UPDATE` như sau:

```sql
UPDATE tên_bảng
SET cột1 = giá_trị1, cột2 = giá_trị2, ...
WHERE điều_kiện;
```

- **tên_bảng**: Tên của bảng mà bạn muốn cập nhật dữ liệu.
- **cột1, cột2, ...**: Tên các cột mà bạn muốn thay đổi.
- **giá_trị1, giá_trị2, ...**: Giá trị mới mà bạn muốn gán cho các cột tương ứng.
- **điều_kiện**: Điều kiện xác định bản ghi nào sẽ được cập nhật. Nếu không có điều kiện, tất cả các bản ghi trong bảng sẽ bị cập nhật.

### Ví dụ
1. Cập nhật một bản ghi:
```sql
UPDATE sinhvien
SET diem = 8.5
WHERE ma_sinh_vien = 12345;
```

2. Cập nhật nhiều cột trong một bản ghi:
```sql
UPDATE sinhvien
SET diem = 9.0, ten = 'Nguyễn Văn A'
WHERE ma_sinh_vien = 12345;
```

3. Cập nhật tất cả bản ghi trong bảng mà không có điều kiện:
```sql
UPDATE sinhvien
SET diem = 7.0;
```

## Giải thích
### Cạm bẫy thường gặp
- **Không sử dụng điều kiện WHERE**: Nếu bạn quên thêm điều kiện `WHERE`, toàn bộ bản ghi trong bảng sẽ bị cập nhật, dẫn đến mất dữ liệu quan trọng.
- **Giá trị NULL**: Cẩn thận khi cập nhật giá trị NULL, vì nó có thể ảnh hưởng đến các phép toán và truy vấn sau này.
- **Quyền truy cập**: Đảm bảo rằng người dùng có quyền `UPDATE` trên bảng tương ứng để tránh lỗi truy cập.

### Ghi chú bổ sung
- Trước khi thực hiện lệnh `UPDATE`, bạn nên sao lưu dữ liệu hoặc kiểm tra cẩn thận bằng cách thực hiện một lệnh `SELECT` với cùng điều kiện để đảm bảo bạn đang cập nhật đúng bản ghi.
- Sử dụng giao dịch (transactions) có thể giúp bạn khôi phục lại trạng thái trước đó nếu có lỗi xảy ra trong quá trình cập nhật.

## Tóm tắt một dòng
Lệnh `UPDATE` trong SQL cho phép người dùng thay đổi dữ liệu trong bảng theo các điều kiện xác định, giúp duy trì tính chính xác của cơ sở dữ liệu.