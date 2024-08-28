---
title : "Cấu hình Customer gateway"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
Tạo Customer gateway
1.	Truy cập vào VPC
    + Chọn **Customer Gateways**
    + Chọn **Create Customer Gateway**
![cgw](/images/3.connect/CGW1.png)
2. Trong giao diện Create Customer Gateway
    + Name tag, nhập **Customer Gateway**
    + IP address, nhập public IP address của Fortigate 100F
    + Chọn Create Customer Gateway
    + Device- Optional : Nhập **Fortigate**
![cgw](/images/3.connect/CGW2.png)
3.	Đợi khoảng 5 phút sau, hoàn tất tạo Customer Gateway
![cgw](/images/3.connect/CGW3.png)