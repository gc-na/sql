<!--
Meta Description: # ALTER: Lệnh Thay Đổi Cấu Trúc Bảng trong SQL ## Tóm tắt Lệnh ALTER trong SQL cho phép người dùng thay đổi cấu trúc của bảng, bao gồm việc thêm, sửa ...
Meta Keywords: đổi, cột, alter, sql, thay
-->

# ALTER: Lệnh Thay Đổi Cấu Trúc Bảng trong SQL

## Tóm tắt
Lệnh ALTER trong SQL cho phép người dùng thay đổi cấu trúc của bảng, bao gồm việc thêm, sửa đổi hoặc xóa các cột và ràng buộc.

## Tài liệu
Lệnh ALTER là một phần quan trọng trong SQL, cho phép quản trị viên cơ sở dữ liệu thực hiện các thay đổi cần thiết trên cấu trúc bảng mà không cần phải xóa và tái tạo lại bảng. Các tính năng chính của lệnh ALTER bao gồm:

- **ALTER TABLE**: Dùng để thay đổi cấu trúc của một bảng hiện có.
- **Thêm cột mới**: Bạn có thể thêm một hoặc nhiều cột vào bảng.
- **Sửa đổi cột**: Cho phép thay đổi kiểu dữ liệu hoặc thuộc tính của một cột.
- **Xóa cột**: Có thể loại bỏ cột không còn cần thiết.
- **Thay đổi tên bảng**: Bạn cũng có thể thay đổi tên của bảng hiện có.

### Cú pháp
```sql
ALTER TABLE tên_bảng
  [Thao_tác_1],
  [Thao_tác_2],
  ...;
```

### Các thao tác hỗ trợ
- **Thêm cột**: 
  ```sql
  ALTER TABLE tên_bảng ADD tên_cột kiểu_dữ_liệu;
  ```
- **Sửa đổi cột**: 
  ```sql
  ALTER TABLE tên_bảng MODIFY tên_cột kiểu_dữ_liệu_mới;
  ```
- **Xóa cột**:
  ```sql
  ALTER TABLE tên_bảng DROP COLUMN tên_cột;
  ```
- **Thay đổi tên bảng**:
  ```sql
  ALTER TABLE tên_bảng RENAME TO tên_mới;
  ```

## Ví dụ
- **Thêm cột mới**:
  ```sql
  ALTER TABLE sinhvien ADD diachi VARCHAR(255);
  ```

- **Sửa đổi cột**:
  ```sql
  ALTER TABLE sinhvien MODIFY hoten VARCHAR(100) NOT NULL;
  ```

- **Xóa cột**:
  ```sql
  ALTER TABLE sinhvien DROP COLUMN diachi;
  ```

- **Thay đổi tên bảng**:
  ```sql
  ALTER TABLE sinhvien RENAME TO hocvien;
  ```

## Giải thích
Khi sử dụng lệnh ALTER, người dùng cần chú ý đến một số điểm quan trọng:

1. **Kết quả không thể phục hồi**: Việc xóa cột sẽ mất dữ liệu trong cột đó. Nên sao lưu dữ liệu trước khi thực hiện thao tác.
2. **Khóa ngoại**: Nếu cột mà bạn muốn xóa có ràng buộc khóa ngoại, bạn sẽ cần phải xóa ràng buộc đó trước khi có thể xóa cột.
3. **Thay đổi kiểu dữ liệu**: Cần đảm bảo rằng các dữ liệu hiện có phù hợp với kiểu dữ liệu mới trước khi thực hiện sửa đổi.
4. **Tùy thuộc vào hệ quản trị CSDL**: Cú pháp và khả năng hỗ trợ có thể thay đổi giữa các hệ quản trị cơ sở dữ liệu như MySQL, PostgreSQL, SQL Server, Oracle, v.v.

## Tóm tắt một dòng
Lệnh ALTER trong SQL cho phép thay đổi cấu trúc bảng, bao gồm việc thêm, sửa đổi và xóa cột hoặc thay đổi tên bảng.