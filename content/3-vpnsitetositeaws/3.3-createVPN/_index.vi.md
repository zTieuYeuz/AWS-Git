---
title : "Cấu hình Site to Site VPN"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3 </b> "
---

Tạo kết nối VPN
1.	Truy cập VPC
    + Chọn **Site-to-Site VPN Connections**
    + Chọn **Create VPN Connection**
![vpn](/images/3.connect/VPNS2S_1.png)
2.	Trong giao diện Create VPN Connection
    + Name tag, nhập VPN Connection to DC
    + Target Gateway Type: Chọn **Virtual Private Gateway**
    + Virtual Private Gateway: Chọn **VPN Gateway**
    + Customer Gateway: **Existing**
    + Customer Gateway ID: Chọn **Customer Gateway**
    + Routing Options: **Dynamic (Requires BGP)**
    + Local IPV4 network CIDR: bạn có thể ko nhập hoặc nhập local IP ở DC. Cụ thể mình nhập **range local 172.16.4.0/24**
    + Remote IPv4 network CIDR: bạn có thể để trống hoặc nhập IP của CIDR aws. Cụ thể ở  đây là **10.10.0.0/16** 
![vpn](/images/3.connect/VPNS2S_2.png)
3.	Tiếp tục thực hiện cấu hình
    + Mở rộng Tunnel 1 options - Optional.
    + Trong tunnel active – Chọn **Enable** để gửi log VPN về **cloudwatch**
    + Amazon CloudWatch log group: chọn **vpns2s/log**
![vpn](/images/3.connect/VPNS2S_3.png)
  + Tương tự Enable trong  tunnel 2 options
  + Chọn Create VPN Connection
![vpn](/images/3.connect/VPNS2S_4.png)
4.	Chọn Create VPN Connection
![vpn](/images/3.connect/VPNS2S_5.png)
5.	Đợi khoảng 5 phút sau, hoàn tất tạo VPN Connection
![vpn](/images/3.connect/VPNS2S_6.png)
6.	Cấu hình propagation cho các route table
    + Trong giao diện VPC, chọn **Route Tables**
    + Chọn **Route table - Public**
    + Chọn **Route Propagation**
    + Chọn **Edit route propagation**
![vpn](/images/3.connect/VPN-Route1.png)
7.	Trong giao diện Edit route propagation
    + Chọn **Enable**
    + Chọn **Save**
![vpn](/images/3.connect/VPN-Route2.png)
8.	Hoàn tất và kiểm tra lại Route Propagation đã chuyển sang Yes
![vpn](/images/3.connect/VPN-Route3.png)
9.	Tương tự Route Propagation đối với Private subnet
![vpn](/images/3.connect/VPN-Route4.png)