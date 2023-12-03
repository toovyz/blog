Bài này mình sẽ dựng một DNS server để phân giải tên miền cho website mình đã dựng trước đó. Sau đó cấp SSL cho website này.

# 1. DNS server

Mình dùng Window Server 2012 làm DNS Server.

## 1.1. Chuẩn bị và cài đặt

Đặt IP tĩnh cho máy.

![image](https://github.com/toovyz/blog/assets/90684283/130ce43f-82ed-41f6-aa81-5736c1925af6)

Tiếp theo, đổi tên cho máy thành VSERVER.

Vào Control Panel\System and Security\System. Chọn `Change Settings` -> Change. Điền tên máy vào ô `Computer name`, sau đó bấm `More`, điền `Primary DNS suffix`, đồng thời là tên domain sau này. Chọn OK và Apply, sau đó khởi động lại máy.

![image](https://github.com/toovyz/blog/assets/90684283/d659bfb6-121a-4112-9cd8-076007608b28)

Vào `Manage` -> `Add Roles and Features`.

![image](https://github.com/toovyz/blog/assets/90684283/02659e5f-dc05-4162-b01d-1da3d393e2f6)

Bấm Next đến `Server Roles` click chọn `DNS Server` -> `Add Features`.

![image](https://github.com/toovyz/blog/assets/90684283/1527ce98-6483-4f3e-9991-2da3e73c1af2)

Next các trang sau và Install.

## 1.2. Cấu hình DNS server

Vào `Tools` -> `DNS`. Tại đây, mình sẽ tạo một Forward Lookup Zone - dùng để phân giải thuận từ địa chỉ ip sang tên miền.

![image](https://github.com/toovyz/blog/assets/90684283/02c367b5-6531-4aef-bdc6-7f3eed4b9a02)

Chuột phải `Forward Lookup Zones` -> `New Zone…`.

![image](https://github.com/toovyz/blog/assets/90684283/f99ebe06-b588-42e5-9021-b7aa0c4feb82)

Các trang trước để mặc định, tại `Zone Name` nhập tên Primary DNS suffix vào ô `Zone name`.

![image](https://github.com/toovyz/blog/assets/90684283/eb925814-7ec2-4095-b380-61e7c6b2e87c)

Tại `Dynamic Update`, chọn `Allow both nonsecure and secure dynamic updates`, sau đó nhấn Next và Finish.

Tiếp theo tạo Reverse Lookup Zones - dùng để phân giải ngược từ tên miền về địa chỉ IP.

Chuột phải `Reverse Lookup Zones` -> `New Zone…`.

Tại `Reverse Lookup Zone Name` nhập tên Primary DNS suffix vào ô `IPv4 Reverse Lookup Zone`, sau đó điền IP của máy vào ô `NetWWork ID`.

![image](https://github.com/toovyz/blog/assets/90684283/78af74b4-0cb7-4e94-8eed-a25fc9bed37c)
![image](https://github.com/toovyz/blog/assets/90684283/96ecff53-9fd1-4ac7-8a52-aea17664374f)

Tại `Dynamic Update`, chọn `Allow both nonsecure and secure dynamic updates`, sau đó nhấn Next và Finish.

![image](https://github.com/toovyz/blog/assets/90684283/ca17ca7c-6172-4676-b6fb-45ebd0809d81)

Chuột phải vào Reverse Lookup Zones mới tạo -> `New Pointer (PTR)`.

![image](https://github.com/toovyz/blog/assets/90684283/b8a75e71-efee-4c69-a03b-7f0a3152d03c)

Browse tới file `vserver.vcore.com` sau đó bấm OK. 

![image](https://github.com/toovyz/blog/assets/90684283/35f53cac-a47c-4e52-8fbc-571e9dc6d965)

Kiểm tra lại.

![image](https://github.com/toovyz/blog/assets/90684283/536b77cf-dba0-4003-a137-5a69dc77edeb)

DNS forwarder sẽ giải quyết yêu cầu, nếu không giải quyết được nó sẽ chuyển tiếp sang DNS forwarder khác​. Mình sẽ forward ra DNS của google (8.8.8.8).

Chuột phải vào Forwarders -> Properties.

![image](https://github.com/toovyz/blog/assets/90684283/f594f74a-f3cd-4d2c-a606-323c29906f4d)

Thêm DNS của google và nhấn OK.

![image](https://github.com/toovyz/blog/assets/90684283/fab24e9f-334d-4eb7-a541-c9a38f799027)

Kết quả: 

![image](https://github.com/toovyz/blog/assets/90684283/72ffda42-f649-43a9-afa0-da9f2fe54968)

# 2. Cấu hình Ubuntu server
## 2.1. Tải các file cần thiết
Tải free ssl tại: https://github.com/toovyz/freessl. Để các file tại `/etc/apache2/ssl`.

![image](https://github.com/toovyz/blog/assets/90684283/54dd41c5-5cc9-4534-a7d0-4787c6a44bf4)

## 2.2. Cấu hình

`nano /etc/apache2/sites-available/relax24h.net.conf`.

![image](https://github.com/toovyz/blog/assets/90684283/5aae66cd-0dcd-4402-8a77-9c087eff48b2)

Vì yêu cầu là tạo web tên là relax24h.net nhưng mình lấy DNS Server cũ là vcore.com nên khi đặt tên file hơi mâu thuẫn tí, mọi người thông cảm :((.

Sau đó chạy `apache2ctl configtest` để kiểm tra, và `systemctl restart apache2` để ấp dụng các cấu hình.

Mở web bằng máy trong LAN:

![image](https://github.com/toovyz/blog/assets/90684283/e941ea0b-8b63-4da7-b1bd-7ce4ea90012f)

Vậy là bài lab đã hoàn thành nhưng chưa hoàn chỉnh:
- Hình như do browser bản cũ quá nên web không load được giao diện như lần trước.
- Mình chưa xin CA từ domain.
Mong rằng mình sẽ có thời gian để update bài lab hoàn chỉnh nhất có thể.
