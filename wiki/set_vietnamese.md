<!--
Meta Description: # Lệnh SET trong SQL: Cách sử dụng và Ví dụ ## Tóm tắt Lệnh SET trong SQL được sử dụng để gán giá trị cho biến, cấu hình các tùy chọn hệ thống hoặc th...
Meta Keywords: set, các, trong, dụng, sql
-->

# Lệnh SET trong SQL: Cách sử dụng và Ví dụ

## Tóm tắt
Lệnh SET trong SQL được sử dụng để gán giá trị cho biến, cấu hình các tùy chọn hệ thống hoặc thiết lập các tham số trong phiên làm việc hiện tại. Đây là một công cụ quan trọng giúp người lập trình quản lý và điều chỉnh hành vi của cơ sở dữ liệu.

## Tài liệu
### Mục đích
Lệnh SET cho phép bạn thiết lập các giá trị cho biến và tham số trong SQL, giúp điều chỉnh cách hoạt động của các truy vấn và phiên làm việc. Nó thường được sử dụng để thay đổi cấu hình của phiên làm việc hoặc để gán giá trị cho các biến tạm thời.

### Cách sử dụng
Cú pháp cơ bản của lệnh SET như sau:

```sql
SET variable_name = value;
```

Trong đó:
- `variable_name` là tên của biến mà bạn muốn gán giá trị.
- `value` là giá trị mà bạn muốn gán cho biến đó.

Ngoài ra, lệnh SET cũng có thể được sử dụng để điều chỉnh các tham số hệ thống, ví dụ:

```sql
SET GLOBAL max_connections = 1000;
```

### Chi tiết
Lệnh SET có thể được sử dụng trong nhiều ngữ cảnh khác nhau, bao gồm:
- Gán giá trị cho các biến tạm thời được sử dụng trong các truy vấn.
- Thay đổi các thiết lập cấu hình toàn cục hoặc cục bộ.
- Thiết lập các tham số cho các hàm hoặc thủ tục.

## Ví dụ
### Ví dụ 1: Gán giá trị cho biến
```sql
SET @myVariable = 10;
SELECT @myVariable; -- Kết quả: 10
```

### Ví dụ 2: Thay đổi tham số hệ thống
```sql
SET SESSION sql_mode = 'STRICT_TRANS_TABLES';
```

### Ví dụ 3: Sử dụng biến trong truy vấn
```sql
SET @userId = 1;
SELECT * FROM users WHERE id = @userId;
```

## Giải thích
### Một số điểm cần chú ý
- Khi sử dụng SET để thay đổi các tham số toàn cục, bạn cần có quyền truy cập tương ứng.
- Các thay đổi mà bạn thực hiện với lệnh SET trong phiên làm việc sẽ không ảnh hưởng đến các phiên khác.
- Một số biến có thể không được gán lại nếu chúng đã được xác định trong một ngữ cảnh khác.

Lệnh SET cũng có thể có các tác động khác nhau tùy thuộc vào hệ quản trị cơ sở dữ liệu mà bạn đang sử dụng (như MySQL, SQL Server hay PostgreSQL), vì vậy bạn nên tham khảo tài liệu cụ thể của hệ quản trị mà bạn đang làm việc.

## Tóm tắt một dòng
Lệnh SET trong SQL được sử dụng để gán giá trị cho biến và cấu hình tham số hệ thống trong phiên làm việc hiện tại.