---
title : "Firewall-Fortigate"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 3.6 </b> "
---

1. Trong bài thực hành này, chúng ta sẽ xây dựng một mô hình  DC theo sơ đồ bên dưới:
### chèn hình ảnh

** lưu ý ở bài lab này mình sử dụng model 100D version  v6.4.12 build2060 (GA)**
 firmware: v6.4.12

 2. Cấu hình ip wan, ip local
 Trong giao diện cấu hình Fortigate:
-	Chọn Network ->  Interface  WAN1 -> Chọn Edit
-	Alias, nhập Wan Internet
-	IP/Netmask, nhập ip ISP cấp 118.107.96.13/24
-	Administrative Access IPv4 check Ping
### chèn hình ảnh
 Tiếp theo ta cấu hình IP Local DC :
-	Chọn Network ->  Interface  LAN(Port6) -> Click Edit
-	IP/Netmask, nhập ip Gw local 172.16.4.1/24
-	Administrative Access IPv4 check Ping
### chèn hình ảnh





    



