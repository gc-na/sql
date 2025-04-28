<!--
Meta Description: # Lệnh DELETE trong SQL: Cách Xóa Dữ Liệu Một Cách An Toàn và Hiệu Quả ## Tóm tắt Lệnh DELETE trong SQL được sử dụng để xóa một hoặc nhiều bản ghi khỏ...
Meta Keywords: xóa, lệnh, bản, delete, liệu
-->

# Lệnh DELETE trong SQL: Cách Xóa Dữ Liệu Một Cách An Toàn và Hiệu Quả

## Tóm tắt
Lệnh DELETE trong SQL được sử dụng để xóa một hoặc nhiều bản ghi khỏi bảng trong cơ sở dữ liệu. Lệnh này rất mạnh mẽ và cần được sử dụng cẩn thận để tránh mất dữ liệu quan trọng.

## Tài liệu

### Mục đích
Lệnh DELETE cho phép người dùng loại bỏ dữ liệu không cần thiết hoặc không còn phù hợp trong bảng. Việc sử dụng lệnh này giúp duy trì tính chính xác và hiệu quả của cơ sở dữ liệu.

### Cú pháp
Cú pháp cơ bản của lệnh DELETE như sau:
```sql
DELETE FROM tên_bảng
WHERE điều_kiện;
```

- **tên_bảng**: Tên của bảng mà bạn muốn xóa dữ liệu.
- **điều_kiện**: Điều kiện xác định bản ghi nào sẽ bị xóa. Nếu không có điều kiện, tất cả các bản ghi trong bảng sẽ bị xóa.

### Chi tiết
- Khi sử dụng lệnh DELETE, bạn cần thận trọng với điều kiện WHERE. Nếu không chỉ định điều kiện, lệnh sẽ xóa tất cả các bản ghi trong bảng.
- Lệnh DELETE không thể khôi phục lại dữ liệu đã xóa trừ khi có bản sao lưu.
- Lệnh DELETE có thể được kết hợp với lệnh JOIN để xóa dữ liệu từ nhiều bảng liên quan.

## Ví dụ

### Ví dụ 1: Xóa một bản ghi cụ thể
```sql
DELETE FROM khach_hang
WHERE id = 1;
```
Lệnh này sẽ xóa bản ghi của khách hàng có id bằng 1.

### Ví dụ 2: Xóa nhiều bản ghi
```sql
DELETE FROM san_pham
WHERE gia < 100;
```
Lệnh này sẽ xóa tất cả sản phẩm có giá dưới 100.

### Ví dụ 3: Xóa tất cả bản ghi trong bảng
```sql
DELETE FROM nhan_vien;
```
Lưu ý: Lệnh này sẽ xóa tất cả bản ghi trong bảng nhan_vien. Hãy sử dụng một cách cẩn thận!

## Giải thích
- **Lỗi phổ biến**: Một trong những sai lầm thường gặp là quên thêm điều kiện WHERE, dẫn đến việc xóa toàn bộ dữ liệu trong bảng. 
- **Khôi phục dữ liệu**: Nếu bạn vô tình xóa nhầm, hãy kiểm tra xem có bản sao lưu dữ liệu không. SQL không cung cấp cách khôi phục tự động cho các bản ghi đã xóa.
- **Phép toán hiệu suất**: Khi xóa nhiều bản ghi, hãy cân nhắc đến hiệu suất của lệnh DELETE, đặc biệt là trong các bảng lớn. 

## Tóm tắt một dòng
Lệnh DELETE trong SQL được sử dụng để xóa bản ghi khỏi bảng, nhưng cần cẩn thận để tránh mất dữ liệu quan trọng.