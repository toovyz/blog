# 1. Tổng quan PCI DSS
Mục tiêu ra đời: khuyến khích và nâng cao bảo mật dữ liệu thẻ thanh toán và tạo điều kiện áp dụng biện pháp bảo mật nhất quán. PCI DSS Cung cấp cơ sở về các yêu cầu kỹ thuật và vận hành để bảo vệ dữ liệu tài khoản. Mặc dù được thiết kế đặc biệt để tập trung vào các môi trường có dữ liệu tài khoản thẻ thanh toán, PCI DSS cũng có thể được sử dụng để  bảo vệ khỏi các mối đe dọa và bảo mật các yếu tố khác trong hệ sinh thái thanh toán.

PCI DSS ược điều hành bởi Payment Card Industry Security Standards Council (PCI SSC) nhằm mục đích đảm bảo an toàn các giao dịch  thẻ tín dụng và thẻ ghi nợ chống lại hành vi trộm cắp và gian lận dữ liệu. PCI SSC thành lập ngày 7 tháng 9 năm 2006 gồm American Express, Discover Financial Services, JCB International, MasterCard và Visa.

Cấu trúc gồm 6 nhóm và 12 yêu cầu:
|                        Nhóm                        |                                                                                                                       Yêu cầu                                                                                                                       |
|:--------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Xây dựng và duy trì mạng và hệ thống an toàn       | 1. Cài đặt và duy trì các biện pháp kiểm soát an ninh mạng. 2. Áp dụng cấu hình bảo mật cho hệ thống.                                                                                                                            |
| Bảo vệ dữ liệu tài khoản                           | 3. Bảo vệ dữ liệu tài khoản được lưu trữ.  4. Bảo vệ dữ liệu chủ thẻ bằng mật mã mạnh trong quá trình truyền qua mạng công cộng.                                                                                                                |
| Duy trì chương trình quản lý lỗ hổng               | 5. Bảo vệ tất cả hệ thống và mạng khỏi mã độc.  6. Phát triển và duy trì các hệ thống và phần mềm bảo mật.                                                                                                                                |
| Thực hiện các biện pháp kiểm soát truy cập mạnh mẽ | 7. Hạn chế quyền truy cập vào các thành phần hệ thống và dữ liệu chủ thẻ.  8. Xác định người dùng và xác thực quyền truy cập vào các thành phần hệ thống.  9. Hạn chế quyền truy cập vật lý vào dữ liệu chủ thẻ. |
| Thường xuyên giám sát và kiểm tra mạng             | 10. Ghi nhật ký và giám sát tất cả quyền truy cập vào các thành phần hệ thống và dữ liệu chủ thẻ.  11. Thường xuyên kiểm tra tính bảo mật của hệ thống và mạng.                                                                                     |
| Duy trì chính sách bảo mật thông tin               | 12. Hỗ trợ bảo mật thông tin bằng các chính sách và chương trình của tổ chức.                                                                                                                                                                       |

# 2. Khả năng áp dụng PCI DSS và thực thể liên quan đến quá trình xử lý thanh toán thẻ
PCI DSS dành cho tất cả các thực thể lưu trữ, xử lý hoặc truyền dữ liệu chủ thẻ (cardholder data - CHD) và dữ liệu xác thực nhạy cảm (sensitive authentication data - SAD) hoặc có thể ảnh hưởng đến tính bảo mật của môi trường dữ liệu chủ thẻ (cardholder data environment - CDE). Yêu cầu PCI DSS áp dụng cho các thực thể có môi trường nơi dữ liệu tài khoản (dữ liệu chủ thẻ và/hoặc dữ liệu xác thực nhạy cảm) được lưu trữ, xử lý hoặc truyền đi và các thực thể có môi trường có thể ảnh hưởng đến tính bảo mật của CDE. Một số yêu cầu PCI DSS cũng có thể áp dụng cho các thực thể có môi trường không lưu trữ, xử lý hoặc truyền dữ liệu tài khoản.

Các thực thể liên quan đến quá trình xử lý thanh toán thẻ:
- Merchant: doanh nghiệp hoặc nhà cung cấp dịch vụ chấp nhận thanh toán bằng thẻ tín dụng từ khách hàng để đổi lấy hàng hóa hoặc dịch vụ.
- Processors: là một công ty làm việc với mạng lưới thẻ và ngân hàng phát hành để ủy quyền, xác thực và giải quyết các giao dịch thẻ tín dụng thay mặt cho doanh nghiệp. Các mạng thẻ tín dụng chính bao gồm Visa, Mastercard, American Express và Discover.
- Acquirers: tổ chức có hợp đồng với người bán và thay mặt họ nhận tiền.
- Issuers: 




