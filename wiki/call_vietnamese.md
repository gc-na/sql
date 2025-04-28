<!--
Meta Description: # CALL trong SQL: Cách Gọi Thủ Tục Lưu Trữ ## Tóm tắt Lệnh `CALL` trong SQL được sử dụng để gọi một thủ tục lưu trữ (stored procedure). Nó cho phép th...
Meta Keywords: thủ, tục, call, gọi, lưu
-->

# CALL trong SQL: Cách Gọi Thủ Tục Lưu Trữ

## Tóm tắt
Lệnh `CALL` trong SQL được sử dụng để gọi một thủ tục lưu trữ (stored procedure). Nó cho phép thực thi các đoạn mã SQL đã được định nghĩa trước, giúp tái sử dụng mã, tối ưu hóa hiệu suất và giữ cho mã nguồn sạch sẽ hơn.

## Tài liệu
### Mục đích
Lệnh `CALL` cho phép người dùng thực hiện các thủ tục lưu trữ đã được định nghĩa trong cơ sở dữ liệu. Thủ tục lưu trữ là một tập hợp các câu lệnh SQL mà có thể được gọi để xử lý các tác vụ cụ thể, chẳng hạn như truy vấn, cập nhật hoặc xóa dữ liệu.

### Cách sử dụng
Cú pháp cơ bản của lệnh `CALL` như sau:
```sql
CALL ten_thu_tuc(param1, param2, ...);
```

Trong đó:
- `ten_thu_tuc`: Tên của thủ tục lưu trữ mà bạn muốn gọi.
- `param1, param2, ...`: Các tham số truyền vào thủ tục (nếu có).

### Chi tiết
- **Thủ tục lưu trữ**: Để sử dụng lệnh `CALL`, trước tiên bạn cần phải định nghĩa một thủ tục lưu trữ trong cơ sở dữ liệu.
- **Tham số**: Thủ tục có thể có các tham số đầu vào và đầu ra. Các tham số đầu vào được sử dụng để truyền dữ liệu vào thủ tục, trong khi các tham số đầu ra có thể được sử dụng để lấy dữ liệu từ thủ tục.
- **Quyền truy cập**: Người dùng cần có quyền gọi thủ tục lưu trữ, nếu không sẽ gặp lỗi khi thực hiện lệnh `CALL`.

## Ví dụ
### Ví dụ 1: Gọi thủ tục không có tham số
```sql
CALL tinh_tong();
```
### Ví dụ 2: Gọi thủ tục với tham số
```sql
CALL tinh_tong_hai_so(10, 20);
```
### Ví dụ 3: Gọi thủ tục với tham số đầu ra
```sql
CALL lay_thong_tin_khach_hang(123, @ten_khach_hang);
SELECT @ten_khach_hang;
```

## Giải thích
- **Lỗi thường gặp**: Một số lỗi có thể xảy ra khi gọi thủ tục lưu trữ, chẳng hạn như sai tên thủ tục hoặc không đủ quyền truy cập.
- **Tham số trống**: Nếu bạn gọi một thủ tục lưu trữ mà không cung cấp đủ tham số, hệ thống sẽ trả về lỗi.
- **Thực thi đồng thời**: Nếu nhiều người dùng cùng gọi thủ tục, cần chú ý đến khả năng đồng bộ hóa và khóa dữ liệu.

## Tóm tắt một câu
Lệnh `CALL` trong SQL cho phép thực thi các thủ tục lưu trữ, giúp tối ưu hóa việc quản lý và xử lý dữ liệu trong cơ sở dữ liệu.