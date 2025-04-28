<!--
Meta Description: # GRANT trong SQL: Cách Cấp Quyền Truy Cập Dữ Liệu ## Tóm tắt Lệnh GRANT trong SQL được sử dụng để cấp quyền truy cập cho người dùng hoặc nhóm người d...
Meta Keywords: quyền, cấp, cho, người, các
-->

# GRANT trong SQL: Cách Cấp Quyền Truy Cập Dữ Liệu

## Tóm tắt
Lệnh GRANT trong SQL được sử dụng để cấp quyền truy cập cho người dùng hoặc nhóm người dùng trên các đối tượng cơ sở dữ liệu, như bảng, chế độ xem, hoặc thủ tục lưu trữ.

## Tài liệu
Lệnh GRANT cho phép quản trị viên cơ sở dữ liệu (DBA) hoặc người dùng có quyền thích hợp cấp quyền cho người khác để thực hiện các hoạt động nhất định trên các đối tượng trong cơ sở dữ liệu. Qua việc cấp quyền, người dùng có thể thực hiện các thao tác như SELECT, INSERT, UPDATE, DELETE, và nhiều quyền khác.

### Cú pháp
```sql
GRANT quyền ON đối_tượng TO người_dùng;
```

- **quyền**: Quyền muốn cấp, như SELECT, INSERT, UPDATE, DELETE, hoặc ALL PRIVILEGES.
- **đối_tượng**: Đối tượng mà quyền được cấp, có thể là bảng, chế độ xem, hoặc thủ tục.
- **người_dùng**: Tên người dùng hoặc nhóm người dùng nhận quyền.

### Ví dụ
1. Cấp quyền SELECT cho người dùng 'user1' trên bảng 'employees':
   ```sql
   GRANT SELECT ON employees TO user1;
   ```

2. Cấp quyền INSERT cho nhóm người dùng 'staff' trên bảng 'orders':
   ```sql
   GRANT INSERT ON orders TO staff;
   ```

3. Cấp tất cả các quyền cho người dùng 'admin' trên bảng 'products':
   ```sql
   GRANT ALL PRIVILEGES ON products TO admin;
   ```

## Giải thích
Khi sử dụng lệnh GRANT, có một số điều cần lưu ý để tránh nhầm lẫn:

- **Quyền kế thừa**: Nếu bạn cấp quyền cho một nhóm người dùng, tất cả các thành viên trong nhóm sẽ nhận quyền đó.
- **Quyền không thể thu hồi**: Để thu hồi quyền đã cấp, bạn cần sử dụng lệnh REVOKE.
- **Quyền cấp cho đối tượng khác nhau**: Các quyền có thể khác nhau tùy theo đối tượng mà bạn đang làm việc. Ví dụ, quyền trên bảng có thể khác với quyền trên chế độ xem.
- **Quyền trên các đối tượng khác nhau**: Không phải tất cả các quyền đều có sẵn cho tất cả các loại đối tượng. Ví dụ, quyền EXECUTE chỉ có thể cấp cho các thủ tục lưu trữ.

## Tóm tắt một dòng
Lệnh GRANT trong SQL cho phép cấp quyền truy cập cho người dùng trên các đối tượng cơ sở dữ liệu nhằm quản lý quyền truy cập và bảo mật dữ liệu hiệu quả.