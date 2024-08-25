---
title : "Tạo kết nối VPN"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.7.3 </b> "
---

1.	Truy cập VPC
    + Chọn Site-to-Site VPN Connections
    + Chọn Create VPN Connection
## chen hình
2.	Trong giao diện Create VPN Connection
    + Name tag, nhập VPN Connection to DC
    + Target Gateway Type: Chọn Virtual Private Gateway
    + Virtual Private Gateway: Chọn VPN Gateway
## chèn hình
3.	Trong giao diện Create VPN Connection
	+ Name tag, nhập VPN Connection to DC
	+ Target Gateway Type: Chọn Virtual Private Gateway
	+ Virtual Private Gateway: Chọn VPN Gateway
	+ Customer Gateway: Existing
    + Customer Gateway ID: Chọn Customer Gateway
    + Routing Options: Dynamic (Requires BGP)
    + Local IPV4 network CIDR: bạn có thể ko nhập hoặc nhập local IP ở DC. Cụ thể mình nhập range local 172.16.4.0/24
    + Remote IPv4 network CIDR: bạn có thể để trống hoặc nhập IP của CIDR aws. Cụ thể ở  đây là 10.10.0.0/16 

## chèn hình

4. 	Tiếp tục thực hiện cấu hình
    + Mở rộng Tunnel 1 options - Optional.
    + Trong tunnel active – Chọn Enable để gửi log VPN về cloudwatch
    + Amazon CloudWatch log group: chọn vpns2s/log
    + Tương tự Enable trong  tunnel 2 options
    + Chọn Create VPN Connection
## chen hình
5. Chọn Create VPN Connection
## chen hình
6. Đợi khoảng 5 phút sau, hoàn tất tạo VPN Connection
## chen hình
7.	Cấu hình propagation cho các route table
    + Trong giao diện VPC, chọn Route Tables
    + Chọn Route table - Public
    + Chọn Route Propagation
    + Chọn Edit route propagation
## chèn hình
8.	Trong giao diện Edit route propagation
    + Chọn Enable
    + Chọn Save
## chen hình
9.	Hoàn tất và kiểm tra lại Route Propagation đã chuyển sang Yes
## chèn hình
10.	Tương tự Route Propagation đối với Private subnet.
## chèn hình





