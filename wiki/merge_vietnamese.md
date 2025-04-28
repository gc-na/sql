<!--
Meta Description: # Lệnh MERGE trong SQL: Hướng dẫn chi tiết và ứng dụng ## Tóm tắt Lệnh MERGE trong SQL cho phép người dùng thực hiện các thao tác cập nhật, chèn hoặc ...
Meta Keywords: source, các, liệu, bảng, trong
-->

# Lệnh MERGE trong SQL: Hướng dẫn chi tiết và ứng dụng

## Tóm tắt
Lệnh MERGE trong SQL cho phép người dùng thực hiện các thao tác cập nhật, chèn hoặc xóa dữ liệu trong bảng một cách đồng thời, dựa trên kết quả của một phép so sánh với một bảng khác. Đây là một công cụ mạnh mẽ giúp tối ưu hóa quy trình thao tác dữ liệu.

## Tài liệu
Lệnh MERGE được sử dụng để đồng bộ hóa dữ liệu giữa hai bảng bằng cách thực hiện các hành động khác nhau (UPDATE, INSERT, DELETE) dựa trên một điều kiện nhất định.

### Mục đích
- Giúp quản lý dữ liệu hiệu quả hơn bằng cách kết hợp nhiều thao tác SQL thành một lệnh duy nhất.
- Cải thiện hiệu suất khi xử lý lượng lớn dữ liệu.

### Cú pháp
Cú pháp cơ bản của lệnh MERGE như sau:
```sql
MERGE INTO target_table AS target
USING source_table AS source
ON target.key_column = source.key_column
WHEN MATCHED THEN
    UPDATE SET target.column1 = source.column1, target.column2 = source.column2
WHEN NOT MATCHED THEN
    INSERT (column1, column2) VALUES (source.column1, source.column2)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

### Các phần trong cú pháp:
- `target_table`: Bảng đích mà bạn muốn cập nhật hoặc chèn dữ liệu.
- `source_table`: Bảng nguồn mà bạn sẽ so sánh dữ liệu.
- `ON`: Điều kiện để xác định các bản ghi khớp.
- `WHEN MATCHED`: Các hành động cần thực hiện khi có bản ghi khớp giữa bảng đích và bảng nguồn.
- `WHEN NOT MATCHED`: Các hành động cần thực hiện khi không có bản ghi khớp.
- `WHEN NOT MATCHED BY SOURCE`: Các hành động cần thực hiện khi có bản ghi trong bảng đích nhưng không có trong bảng nguồn.

## Ví dụ
### Ví dụ 1: Cập nhật dữ liệu
```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN MATCHED THEN
    UPDATE SET target.salary = source.salary
WHEN NOT MATCHED THEN
    INSERT (employee_id, salary) VALUES (source.employee_id, source.salary);
```

### Ví dụ 2: Xóa dữ liệu không còn trong bảng nguồn
```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

## Giải thích
### Những lưu ý thường gặp:
- Đảm bảo rằng các điều kiện trong mệnh đề ON là chính xác để tránh xóa hoặc cập nhật dữ liệu không mong muốn.
- Lệnh MERGE không phải là một lệnh chuẩn trong tất cả các hệ quản trị cơ sở dữ liệu SQL, vì vậy cần kiểm tra tính tương thích với hệ quản trị mà bạn đang sử dụng.
- Sử dụng lệnh MERGE có thể làm giảm hiệu suất nếu bảng có nhiều bản ghi hoặc điều kiện phức tạp.

### Các vấn đề có thể gặp phải:
- Nếu không có điều kiện rõ ràng trong mệnh đề ON, có thể dẫn đến việc không thực hiện các hành động cần thiết.
- Cần cẩn thận với các thao tác DELETE, vì chúng có thể xóa nhiều bản ghi không mong muốn nếu không được cấu hình đúng.

## Tóm tắt một dòng
Lệnh MERGE trong SQL cho phép thực hiện đồng thời các thao tác cập nhật, chèn và xóa dữ liệu giữa hai bảng dựa trên điều kiện so sánh.