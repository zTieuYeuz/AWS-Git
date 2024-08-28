---
title : "Kiểm tra tình trạng VPN"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---
1. Truy cập vào cloudwatchlog để xem log về phase 1 phase 2 của vpn
      + Tại giao diện **cloudwatch** , chọn **Log groups**, chọn **vpns2s/log**, chọn log 1 tunnel và kiểm tra trạng thái đã thiết lập VPN 
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-0.png)
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-01.png)
2.	Kiểm tra trạng thái tunnel :
      + Trạng thái tunnel của vpn up trên Fortigate
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-1.png)
      + Trạng thái VPN trên aws 
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-2.png)
3.	Kiểm tra bảng định tuyến 
      + Bảng routes trên aws sẽ tự xuất hiện subnet của DC
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-3.png)
      + Trên giao diện Fortigate chọn Dashboard chọn + nhập Routing rồi chọn + , sau đó chọn Add Monitor để tạo bảng monitor routing
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-4.png)
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-5.png)
      + Dashboard chọn Routing Monitor xem sự xuất hiện của Subnet aws trên Fortigate 
![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-6.png)
** **lưu ý ở đây : mình chỉ thấy có 1 route duy nhất cho interface VPN AWS Tunnel1 do route mình đang xài dynamic nên cả 2 site Fortigate và AWS sẽ tự động hóa chọn 1 tunnel để truyền dữ liệu. Tunnel 2 sẽ ở trạng thái backup khi có downtime ở tunnel 1 trên aws** ** 