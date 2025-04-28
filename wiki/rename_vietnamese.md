<!--
Meta Description: # Lệnh RENAME trong SQL: Cách Đổi Tên Bảng và Cột ## Tóm tắt Lệnh RENAME trong SQL được sử dụng để thay đổi tên của các đối tượng cơ sở dữ liệu như bả...
Meta Keywords: tên, đổi, rename, bạn, liệu
-->

# Lệnh RENAME trong SQL: Cách Đổi Tên Bảng và Cột

## Tóm tắt
Lệnh RENAME trong SQL được sử dụng để thay đổi tên của các đối tượng cơ sở dữ liệu như bảng và cột, giúp quản lý và tổ chức dữ liệu một cách hiệu quả hơn.

## Tài liệu
Lệnh RENAME là một phần quan trọng trong SQL, cho phép người dùng đổi tên các đối tượng trong cơ sở dữ liệu mà không cần phải tạo lại chúng. Việc đổi tên có thể giúp cải thiện tính rõ ràng và dễ hiểu của cấu trúc cơ sở dữ liệu.

### Mục đích
- Giúp tăng cường khả năng quản lý và tổ chức dữ liệu.
- Cải thiện tính dễ hiểu cho các đối tượng trong cơ sở dữ liệu.

### Cú pháp
Cú pháp của lệnh RENAME có thể khác nhau tùy thuộc vào hệ quản trị cơ sở dữ liệu (DBMS) mà bạn đang sử dụng. Dưới đây là cú pháp cơ bản:

```sql
-- Đổi tên bảng
RENAME TABLE ten_bang_cu TO ten_bang_moi;

-- Đổi tên cột
ALTER TABLE ten_bang
RENAME COLUMN ten_cot_cu TO ten_cot_moi;
```

## Ví dụ
### Ví dụ 1: Đổi tên bảng
Giả sử bạn có một bảng có tên là `khach_hang` và bạn muốn đổi tên thành `khach_hang_moi`:

```sql
RENAME TABLE khach_hang TO khach_hang_moi;
```

### Ví dụ 2: Đổi tên cột
Nếu bạn có một bảng `san_pham` với cột `gia_cu` và bạn muốn đổi tên nó thành `gia_moi`:

```sql
ALTER TABLE san_pham
RENAME COLUMN gia_cu TO gia_moi;
```

## Giải thích
Mặc dù lệnh RENAME rất hữu ích, nhưng có một số điều cần lưu ý:

- **Quyền truy cập**: Đảm bảo bạn có đủ quyền để thay đổi tên của bảng hoặc cột.
- **Ràng buộc và chỉ mục**: Khi bạn đổi tên cột, hãy kiểm tra các ràng buộc và chỉ mục liên quan, vì chúng có thể bị ảnh hưởng.
- **Tác động đến mã nguồn**: Nếu bạn có mã nguồn hoặc truy vấn sử dụng tên cũ, bạn cần cập nhật chúng để tránh lỗi.

## Tóm tắt một câu
Lệnh RENAME trong SQL cho phép bạn đổi tên bảng và cột, giúp quản lý và tổ chức cơ sở dữ liệu hiệu quả hơn.