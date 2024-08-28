---
title : "Tạo BGP"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---
1.	Trong giao diện cấu hình Fortigate bạn cấu hình luôn routing cho cả 2 tunnel theo file:
      + Chọn Network -> Chọn BGP
      + Router-ID nhập 118.107.96.13
      + Chọn Apply
![bgp](/images/4.vpnsitetositefortigate/BGP-1.png)
      + Neighbor chọn Create new. Hộp Add Neighbor hiện ra để cấu hình tunnel 1
      + IP nhập 169.254.52.5, Remote AS nhập 64512 
![bgp](/images/4.vpnsitetositefortigate/BGP-2.png)
      + IP/Netmask nhập 172.16.4.0/24. Đây là dải địa chỉ được Fortigate dùng để quảng bá cho AWS\
**lưu ý ở chỗ này cấu hình khác với trong file**
![bgp](/images/4.vpnsitetositefortigate/BGP-3.png)
2.	Cấu hình neighbors cho tunnel 2
      + Neighbors chọn Create New. Hộp Add Neighbor hiện ra để cấu hình tunnel 2
![bgp](/images/4.vpnsitetositefortigate/BGP-4.png)
      + IP nhập **169.254.52.5**, Remote AS nhập 64512 -> Chọn OK 
      + Chọn **Apply**
![bgp](/images/4.vpnsitetositefortigate/BGP-5.png)