<!--
Meta Description: # TRUNCATE: Lệnh Truncate trong SQL - Xóa Dữ Liệu Nhanh Chóng ## Tóm Tắt Lệnh TRUNCATE trong SQL được sử dụng để xóa tất cả các bản ghi trong một bảng...
Meta Keywords: truncate, trong, bảng, xóa, không
-->

# TRUNCATE: Lệnh Truncate trong SQL - Xóa Dữ Liệu Nhanh Chóng

## Tóm Tắt
Lệnh TRUNCATE trong SQL được sử dụng để xóa tất cả các bản ghi trong một bảng mà không xóa cấu trúc của bảng đó. Đây là một phương pháp hiệu quả để làm sạch dữ liệu, thường được sử dụng khi cần xóa toàn bộ dữ liệu mà không cần phải ghi lại từng bản ghi.

## Tài Liệu
### Mục Đích
Lệnh TRUNCATE giúp người dùng xóa tất cả các bản ghi trong bảng một cách nhanh chóng và hiệu quả hơn so với lệnh DELETE. Khi sử dụng TRUNCATE, không có bản ghi nào sẽ được ghi vào log giao dịch, do đó, tốc độ thực hiện nhanh hơn.

### Cách Sử Dụng
Cú pháp cơ bản của lệnh TRUNCATE như sau:

```sql
TRUNCATE TABLE tên_bảng;
```

Trong đó `tên_bảng` là tên của bảng mà bạn muốn xóa dữ liệu.

### Chi Tiết
- TRUNCATE không thể được sử dụng khi bảng có khóa ngoại tham chiếu đến nó.
- Lệnh này không thể được hoàn tác (ROLLBACK) nếu không sử dụng trong một giao dịch (transaction).
- Cấu trúc của bảng (bao gồm các cột và thuộc tính) vẫn được giữ nguyên, chỉ dữ liệu bên trong bảng bị xóa.
- Lệnh TRUNCATE thường được sử dụng trong các tình huống như dọn dẹp dữ liệu trước khi nhập dữ liệu mới.

## Ví Dụ
### Ví dụ 1: Xóa tất cả dữ liệu trong bảng
```sql
TRUNCATE TABLE KhachHang;
```
Lệnh này sẽ xóa tất cả các bản ghi trong bảng `KhachHang` mà không làm mất đi cấu trúc của bảng.

### Ví dụ 2: Sử dụng trong một giao dịch
```sql
BEGIN TRANSACTION;
TRUNCATE TABLE SanPham;
-- Một số thao tác khác
ROLLBACK; -- Không thể hoàn tác TRUNCATE
```
Trong ví dụ này, TRUNCATE sẽ không thể hoàn tác và dữ liệu bị mất vĩnh viễn.

## Giải Thích
- **Lưu ý về Khóa Ngoại:** Nếu bảng có các mối quan hệ khóa ngoại, bạn sẽ không thể sử dụng TRUNCATE cho bảng đó. Bạn cần phải xóa các ràng buộc khóa ngoại trước khi thực hiện.
- **So sánh với DELETE:** Lệnh DELETE có thể xóa từng bản ghi và có thể được hoàn tác, trong khi TRUNCATE là một quá trình nhanh hơn nhưng không thể hoàn tác.
- **Chỉ số và Bộ Đếm:** Lệnh TRUNCATE cũng sẽ đặt lại bộ đếm cho các cột tự động tăng (AUTO_INCREMENT) về giá trị ban đầu.

## Tóm Tắt Một Dòng
Lệnh TRUNCATE trong SQL là một phương pháp hiệu quả để xóa tất cả các bản ghi trong bảng mà không làm mất cấu trúc bảng, giúp tăng tốc độ xử lý.