---
title : "Tạo tunnel IPsec"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.8.1 </b> "
---
1.	Truy cập vào VPC
    + Chọn Site-to-Site VPN Connection
    + Chọn VPN Connection đã tạo
    + Chọn Download Configuration
## chèn hình
2.	Trong hộp thoại Download Configuration, lựa chọn appliance phù hợp với bạn: Trong bài thực hành này, chúng ta sẽ sử dụng Fortigate.
    + Vendor: Chọn Fortinet
    + Platform: Chọn Fortigate 40+series
    + Software: Chọn FortiOS 6.4.4+ (GUI)
    + IKE version: Chọn ikev1
    + Chọn Download.
## chèn hình
3.	Lưu thông tin file câu hình vào thư mục:
    + Sau đó dựa vào cấu hình được cung cấp, bạn cấu hình các thông tin này cấu cho thiết bị của mình.
## chèn hình
Lưu ý ở bước về sau ta sẽ cấu hình các thông số này ở thiết bị firewall lần lượt theo thứ tự sau:
+ Cấu hình Phase 1 cho Ip sec tunnel1
+ Cấu hình Phase 2 cho Ipsec Tunnel1
+ Cấu hình interface tunnel
+ Cấu hình routing BGP
+ Cấu hình Policy cho phép AWS và local DC giao tiếp được với nhau
+ Lặp từ bước 1 đến 5 cho 
4.	Tại giao diện Fortigate tạo tunnel 1 VPN:
    + Chọn VPN -> IPsec Wizard
    + Template type chọn Custom
    + Name nhập VPN AWS Tunnel 1
    + Chọn Next
## chen hình
5.	Tại giao diện New VPN Tunnel bạn tạo tunnel 1 cho VPN :
#### ***5.1 Phase 1***
  + IP address nhập 18.143.226.251
  + Interface chọn Wan Internet(Wan 1)
  + NAT Traversal chọn Disable
  + Pre-shared Key nhập thông số như trong file DS6CXQf8YMvA0E4wRo4uDGRtcVofGiad
  + Phase 1 Proposal bạn xóa hết các dòng trước đó và cấu hình Encryption chọn AES128, Authentication chọn SHA1  
  + Diffie-Hellman Groups bỏ chọn 14,5 . Chỉ chọn 2 
  + Key Lifetime (seconds) nhập 28800
## chen hình

#### ***5.2 phase 2***
  + Phase 2 Selectors Chọn Vùng Phase2
  + Phase 2 Proposal xóa toàn bộ các dòng trước đó và cấu hình Encryption chọn 
  + Diffie-Hellman Groups bỏ chọn 14,5 . Chỉ chọn 2 
  + Chọn Auto-negotiate
  + Seconds nhập 3600
  + Chọn OK để tạo
## chèn hình
6.	Tại giao diện New VPN Tunnel bạn làm tương tự cho tunnel 2 như tunnel 1:
## chèn hình
kết quả
## chèn hình
7. Cấu hình interface tunnel1,2
8. Trong giao diện cấu hình Fortigate:
    + Chọn Network ->  Interface  WAN1 -> Chon + -> Chọn VPN AWS Tunnel 1 -> Chọn Edit
    + IP nhập  169.254.52.6
    + Remote IP/Netmask nhập 169.254.52.5/30
    + Administrative Access chọn Ping
    + Status chọn Enable
    + Chọn OK
## chèn hình
cấu hình tunnel 2 tường tự
## chèn hình
8. Cấu hình routing BGP\
 ** Lưu ý ở bước các bạn dựa vào phần **“#4: Border Gateway Protocol (BGP) Configuration”** có trong nội dung file cấu hình đã tải trước đó**
   + Trong giao diện cấu hình Fortigate bạn cấu hình luôn routing cho cả 2 tunnel theo file:
   + Chọn Network -> Chọn BGP
   + Router-ID nhập 118.107.96.13
   + Chọn Apply
## chèn hình
   + Neighbor chọn Create new. Hộp Add Neighbor hiện ra để cấu hình tunnel 1
## chèn hình
   + Neighbor chọn Create new. Hộp Add Neighbor hiện ra để cấu hình tunnel 1,IP nhập 169.254.52.5, Remote AS nhập 64512 
## chèn hình
   + IP/Netmask nhập 172.16.4.0/24. Đây là dải địa chỉ được Fortigate dùng để quảng bá cho AWS.

** lưu ý ở chỗ này cấu hình khác với trong file **
## chèn hình
9. Cấu hình neighbors cho tunnel 2
    + Neighbors chọn Create New. Hộp Add Neighbor hiện ra để cấu hình tunnel 1
    + IP nhập 169.254.52.5, Remote AS nhập 64512 -> Chọn OK 
    + Chọn Apply
## chèn hình
10. Tạo các policy\
Mặc định Firewall sẽ chặn tất cả lưu lương mạng ở tất cả các cổng. Ở phần này bạn sẽ mở chính sách truy cập ở cả 2 chiều của VPN trên cả 2 tunnel\
** Lưu ý ở bước các bạn dựa vào phần #5: Firewall Policy Configuration” có trong nội dung file cấu hình đã tải trước đó.**\
**Cấu hình mở chính sách truy cập VPN lên aws cho tunnel 1. Trong giao diện cấu hình Fortigate:**
    + Chọn Policy & Objects
    + Chọn Firewall Policy
    + Chọn Create New
    + Name nhập DC TO AWS Tunnel 1
    + Incoming Interface chọn LAN(Port6)
    + Outgoing Interface chọn VPN AWS Tunnel1
    + Source chọn All
    + Destination chọn All
    + Service chọn All
    + NAT chọn uncheck
    + Log Allowed Traffic chọn ALL Sessions. Để có ghi nhận lại nhật ký truy cập
    + Chọn OK
## chèn hình
11.	Cấu hình mở chính sách truy cập từ AWS về DC cho tunnel 1. Trong giao diện cấu hình Fortigate:
    + Chọn Policy & Objects
    + Chọn Firewall Policy
    + Chọn Create New
    + Name nhập AWS TO DC Tunnel 1
    + Incoming Interface chọn VPN AWS Tunnel1
    + Outgoing Interface chọn LAN(Port6)
    + Source chọn All
    + Destination chọn All
    + Service chọn All
    + NAT chọn uncheck
    + Log Allowed Traffic chọn ALL Sessions. Để có ghi nhận lại nhật ký truy cập
    + Chọn OK
## chèn hình
12.	Cấu hình mở chính sách truy cập tương tự cho tunnel 2 ở 2 chiều. Ở phần này các bạn tự cấu hình tương tự sau khi xong bạn sẽ có tổng cộng 4 policy.
## chèn hình
13.	Kiểm tra tình trạng VPN\
Truy cập vào cloudwatchlog để xem log về phase 1 phase 2 của vpn
    + Tại giao diện cloudwatch , chọn Log groups, chọn vpns2s/log, chọn log 1 tunnel và kiểm tra trạng thái đã thiết lập VPN 
## chèn hình
14.	Kiểm tra trạng thái tunnel :
    + Trạng thái tunnel của vpn up trên Fortigate (chèn hình)
    + trạng thái vpn trên aws (chèn hình)
    + Kiểm tra bảng định tuyến 
        - Kiểm tra bảng định tuyến (chèn hinh)
        - Trên giao diện Fortigate chọn Dashboard chọn +  nhập Routing rồi chọn + , sau đó chọn Add Monitor để tạo bảng monitor routing (chèn hình)
        - Dashboard chọn Routing Monitor xem sự xuất hiện của Subnet aws trên Fortigate (chèn hình)\
> ** lưu ý ở đây : mình chỉ thấy có 1 route duy nhất cho interface VPN AWS Tunnel1 do route mình đang xài dynamic nên cả 2 site Fortigate và AWS sẽ tự động hóa chọn 1 tunnel để truyền dữ liệu. Tunnel 2 sẽ ở trạng thái backup khi có downtime ở tunnel 1 trên aws ** 
15. Kiểm tra tình trang VPN
    + Kiểm tra ping từ DC lên EC2 Private (chèn hình)
    + Kiểm tra ping từ Aws về PC ở DC (chen 2hinh)











