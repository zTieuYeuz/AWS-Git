---
title : "Cấu hình virteal private Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

Tạo Virtual Private Gateway
1.	Truy cập vào VPC
    + Chọn **Virtual Private Gateway**
    + Chọn **Create Virtual Private Gateway**
![vpg](/images/3.connect/Virtual%20private%20GW.png)
2.	Trong giao diện Create Virtual Private Gateway
    + Name tag, nhập **VPN TO DC**
    + Chọn Amazon default ASN
    + Chọn Create virtual private gateway
![vpg](/images/3.connect/Virtual%20private%20GW2.png)
3. Chúng ta cần thực hiện Attach to VPC
    + Chọn **Actions**
    + Chọn **Attach to VPC**
![vpg](/images/3.connect/Virtual%20private%20GW3.png)
4. Trong giao diện Attach to VPC
    + Chọn **VPC ASG.**
    + Chọn **Attach to VPC**\
**Virtual private**
![vpg](/images/3.connect/Virtual%20private%20GW4.png)
5.	Hoàn tất và xem State là Attached
![vpg](/images/3.connect/Virtual%20private%20GW5.png)