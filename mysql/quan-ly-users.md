# 🤢 Quản lý users

## Lấy ra tất cả user hiện có&#x20;

```sql
SELECT user, host FROM mysql.user;
```

## Thêm user

<pre class="language-sql"><code class="lang-sql"><strong>CREATE USER 'username'@'host' IDENTIFIED WITH mysql_native_password BY 'password';</strong></code></pre>

> Sau khi tạo user mới thường sẽ cần cấp quyền cho user này

## Xóa user

```sql
DROP USER 'username'@'host' --[, "username"@"host", ...]
```

## Cấp quyền cho user

```sql
-- Chỉ định rõ quyền nào trên database nào và table nào
GRANT PRIVILEGE ON database.table TO 'username'@'host';
-- Cấp quyền trên tất cả
GRANT ALL PRIVILEGES ON *.* TO 'username'@'host' WITH GRANT OPTION;

FLUSH PRIVILEGES;
```
