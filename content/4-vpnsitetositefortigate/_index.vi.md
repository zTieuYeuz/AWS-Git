---
title : "Cấu hình VPN Site to Site Trên Fortigate"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4 </b> "
---

Trước khi cấu hình chúng ta tìm hiểu sơ qua về giao thức định tuyến động **BGP**. Vì sao nên dùng **BGP**.

**Border Gateway Protocol (BGP)** là một giao thức định tuyến **động** được sử dụng trong mạng Internet để trao đổi thông tin giữa các mạng con (networks) khác nhau. Đây là một trong những giao thức quan trọng nhất giúp các hệ thống mạng trao đổi thông tin và xác định con đường tối ưu để chuyển tiếp dữ liệu. BGP được thiết kế để hoạt động trong các hệ thống mạng lớn, đặc biệt trong mạng lưới Internet toàn cầu, nơi hàng có trăm nghìn mạng con cần liên kết với nhau.
**BGP** có khả năng xác định con đường chuyển tiếp dữ liệu dựa trên nhiều thuộc tính như băng thông, chất lượng và số lượng các đường truyền mạng con mà dữ liệu cần đi qua. Điều này giúp giao thức chọn ra đường tối ưu nhất để truyền dữ liệu từ nguồn đến đích một cách hiệu quả và nhanh chóng.

Bên cạnh đó, BGP có vai trò giữ cho Internet hoạt động một cách ổn định bằng cách cập nhật thông tin định tuyến định kỳ, đáng tin cậy và linh hoạt.
BGP là lựa chọn tốt cho các mạng lớn, phức tạp và cần khả năng tự động, linh hoạt nếu có nhiều networks. So sánh với static route thì BGP ưu điểm vượt trội hơn:

| **Thuộc tính**                 | **BGP (Border Gateway Protocol)**          | **Static Route (Định tuyến tĩnh)**     |
|:----------------------------:|:------------------------------------------:|:--------------------------------------:|
| **Tính tự động và linh hoạt**| Tự động học và điều chỉnh tuyến đường khi có thay đổi trong mạng. | Cần cấu hình thủ công mọi tuyến đường, cần cập nhật thủ công khi có thay đổi. |
| **Khả năng mở rộng**         | Thích hợp cho mạng lớn, xử lý hàng triệu tuyến đường. | Phù hợp cho mạng nhỏ hoặc đơn giản, khó quản lý khi mạng mở rộng. |
| **Chính sách định tuyến**    | Hỗ trợ các chính sách định tuyến phức tạp dựa trên nhiều thuộc tính. | Không hỗ trợ chính sách định tuyến phức tạp. |
| **Khả năng phục hồi**        | Tự động chuyển đổi tuyến đường khi gặp sự cố, đảm bảo phục hồi nhanh chóng. | Phải cấu hình thủ công các tuyến đường dự phòng, không linh hoạt. |
| **Bảo mật**                  | Hỗ trợ cơ chế bảo mật như MD5, nhưng yêu cầu quản lý phức tạp. | Đơn giản hơn, ít bị tấn công hơn nhưng vẫn có thể cấu hình sai. |
| **Tình huống sử dụng**       | Thích hợp cho mạng lớn, phức tạp, nhiều ISP, cần tự động và phục hồi nhanh. | Phù hợp cho mạng nhỏ, đơn giản, không cần tự động hóa hay phục hồi phức tạp. |


### Nội dung
  - [Tạo tunnel IP Sec](4.1-createtunnel/)
  - [Cấu hình interface tunnel 1 và tunnel 2](4.2-configinterfacetunnel/)
  - [Cấu hình routing BGP](4.3-configroutingbgp/)
  - [Tạo các policy cho VPN](4.4-createpolicy/)
  - [Kiểm tra tình trạng VPN ](4.5-checkstatusvpn/)

