Dựng một webserver trên ubuntu với:
- Web server: Apache2.
- Database: MariaDB.
- CMS: Wordpress.
# 1. Cài đặt các package cần thiết
## 1.1. Apache2 server
```
sudo apt update
sudo apt install apache2
```

![image](https://github.com/toovyz/blog/assets/90684283/f04ee3be-d137-4a8d-9ba9-e3e589d6efb5)

## 1.2. MariaDB
```
sudo apt update
sudo apt install mariadb-server mariadb-client
```

![image](https://github.com/toovyz/blog/assets/90684283/aaf10608-3999-4859-bd20-32bcc009132d)


## 1.3. PHP
```
sudo apt -y install php-{cli,fpm,bcmath,curl,gd,imagick,mbstring,mysql,redis,soap,xml,zip}
```

![image](https://github.com/toovyz/blog/assets/90684283/53bc1e88-0a91-4a60-a13e-e9e44c2a618c)

## 1.4. Wordpress
```
cd /tmp
wget https://wordpress.org/latest.tar.gz
tar xvaf latest.tar.gz
```

# 2. Tạo website bằng wordpress
## 2.1. Tạo database và user wordpress
Dùng câu lệnh `mysql` để khởi động database.

Tạo database wordpress: `create database wordpress;`.

Tạo user wordpress: `create user 'wordpress'@'localhost' identified by '123';`.

Cấp quyền cho user: `grant all on wordpress.* to 'wordpress'@'localhost' with grant option;`.

Lưu lại: `flush privileges;`.

![image](https://github.com/toovyz/blog/assets/90684283/28a50d54-d27f-41ef-b3df-d295789ffc04)
![image](https://github.com/toovyz/blog/assets/90684283/49ce32d6-7b1c-4c14-8446-cf2ca4e1ef0b)

## 2.2. Cấu hình Apache2 và WordPress
Di chuyển file wordpress vào `/var/www/`.
```
mv /tmp/wordpress /var/www//wordpress
cd /
sudo chown -R www-data:www-data /var/www/wordpress/
sudo chmod -R 755 /var/www/wordpress/
```
Cấu hình wordpress và apache2.
```
sudo nano /etc/apache2/sites-available/wordpress.conf
```

![image](https://github.com/toovyz/blog/assets/90684283/7bc565a4-6170-4896-8d09-9349bce73790)


Cấu hình file wp-config.php.
```
cd /var/www/wordpress
sudo mv wp-config-sample.php wp-config.php
sudo nano wp-config.php
```

![image](https://github.com/toovyz/blog/assets/90684283/2ae41231-d2a0-4d3a-9898-94cdaf8ae5c3)

Khởi động Wordpress.
```
sudo a2ensite wordpress.conf
sudo a2enmod rewrite
sudo systemctl restart apache2.service
```
Sau khi khởi động, vào browser gõ địa chỉ IP của máy server sẽ xuất hiện trang chủ wordpress ---> thành công.





  







