---
title : "Tạo tunnel 1-2 tren Fortigate"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---
Trong giao diện cấu hình Fortigate:
1. cấu hình Tunnel 1
   + Network ->  Interface  WAN1 -> Chon + -> Chọn VPN AWS  Tunnel 1 -> Chọn Edit
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface1.png)
   + IP nhập  **169.254.52.6**
   + Remote IP/Netmask nhập **169.254.52.5/30**
   + **Administrative Access chọn Ping**
   + **Status chọn Enable**
   + Chọn **OK**
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface2.png)
2. Cấu hình tunnel 2
   + IP nhập  **169.254.52.6**
   + Remote IP/Netmask nhập 1**69.254.52.5/30**
   + **Administrative Access chọn Ping**
   + **Status chọn Enable**
   + Chọn **OK**
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface3.png)
3. 2 đường tunnel đã tạo
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface4.png)