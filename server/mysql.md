# 📦 Mysql

## Cài đặt Mysql

### Standalone

### Xampp

Tải file cài đặt từ trang chủ [Xampp ](https://www.apachefriends.org/)về và cài như app Windows thông thường

### Bitnami Nginx Stack

Tải file cài đặt từ trang [Bitnami Nginx Stack](https://bitnami.com/stack/nginx) về và cài như app Windows thông thường

## Một số lưu ý khi setup Mysql

### Mở cổng 3306

Nhớ mở cổng 3306 để có thể connect tới Mysql từ bên ngoài server

> Chỉ nên mở cho một số host cụ thể (cùng với đó là mỗi host nên [có một user riêng](../database/mysql/quan-ly-users.md#them-user) và [quyền cụ thể](../database/mysql/quan-ly-users.md#cap-quyen-cho-user) để tránh tình trạng bị lộ thông tin và mất dữ liệu)

#### Centos

```bash
iptables -I INPUT -p tcp -s xxx.xxx.xxx.xxx --dport 3306 -j ACCEPT
```

### Mysql Client

Phổ biến và dễ dùng nhất là [PHPMyadmin ](https://www.phpmyadmin.net/)và [Navicat](https://www.navicat.com/en/) (Mysql Workbench dùng như 💩, Table Plus cũng hay nhưng mà MacOS mới có 😭)

#### PHPMyadmin

Cái này cực kỳ dễ dùng, là một Mysql Client trên nền web, setup cực kì đơn giản:

* (Optional) Nếu dùng **Xampp** thì không cần cài gì cả (bỏ qua tất cả các bước dưới), bật Mysql lên rồi chọn `Admin` của dòng Mysql ở trong GUI của Xampp là được
* Download source từ trang chủ về
* Giải nén
* Nếu dùng **Nginx**: Config một domain trỏ đến htdocs của folder code PHPMyadmin đã giải nén ở trên là xong

#### Navicat

Cái này mất tiền (khá đắt nhưng crack lại rất dễ 😏), giao diện đẹp, thân thiện và rất dễ dùng

Cài đặt như các app Windows thông thường thôi
