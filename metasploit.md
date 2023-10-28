Metasloit là freamwork mã nguồn mở hỗ trợ tấn công và khai thác những lỗ hổng trên nhiều loại hệ thống khác nhau.
Một số key quan trọng:
* LHOST: IP của attacker.
* RHOST: IP của victim.
* LPORT: Port mở ra nhận thông tin máy attacker.
* RPORT: Port trên máy victim.
Trong lần khởi động đầu tiên, chạy các lệnh sau:

Khởi động database để lưu lại quá trình pentest.

<img width="472" alt="Screenshot 2023-10-28 at 15 23 59" src="https://github.com/toovyz/blog/assets/90684283/643d86d7-b7b7-4db0-954f-babdc6212c65">

Gõ lệnh `msf init` để tạo cơ sở dữ liệu.

<img width="695" alt="Screenshot 2023-10-28 at 15 25 47" src="https://github.com/toovyz/blog/assets/90684283/541b7813-1f6b-4117-81d0-13eda4575794">

Khỏi động metasploit bằng lệnh `msfconsole`.

<img width="687" alt="Screenshot 2023-10-28 at 15 30 52" src="https://github.com/toovyz/blog/assets/90684283/251b33a1-2528-40e8-88af-49e5656c5a50">

Kiểm tra kết nối với database bằng `db_status`.

<img width="522" alt="Screenshot 2023-10-28 at 15 32 58" src="https://github.com/toovyz/blog/assets/90684283/0908decf-415a-4de3-9df9-2ab7deb44ded">


# Scan port
Path tới script scan port: `/usr/share/metasploit-framework/modules/auxiliary/scanner/portscan`.

<img width="816" alt="Screenshot 2023-10-28 at 15 04 52" src="https://github.com/toovyz/blog/assets/90684283/3e05e0a3-714b-463d-9003-85fb0c1f6a22">
