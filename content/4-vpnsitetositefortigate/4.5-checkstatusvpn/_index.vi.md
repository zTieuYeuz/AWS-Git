---
title : "Kiểm tra tình trạng VPN"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---

1. Truy cập vào cloudwatchlog để xem log về phase 1 phase 2 của vpn
   [Tại giao diện CloudWatch](https://ap-southeast-1.console.aws.amazon.com/cloudwatch/home)
   +  Chọn **Log groups**, chọn **vpns2s/log**, mỗi **Log streams** đại diện cho 1 tunnel.
   +  Nếu trạng thái của **ike_phase1_state** và **ike_phase2_state** đều là **established**. Thì tức là VPN đã **up**. Nếu không hãy dựa vào logs trên này để xác minh lỗi.
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-0.png)
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-01.png)

2. Để chắc chắn bạn kiểm tra trạng thái **tunnel** ở giao diện cả 2 site:
   + Trạng thái **tunnel** của vpn up trên **Fortigate**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-1.png)
   + Trạng thái **VPN** trên **aws**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-2.png)
3. Kiểm tra **bảng định tuyến** 
   + Bảng **định tuyến** trên **aws** sẽ tự xuất hiện subnet **172.16.4.0/24** của **DC**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-3.png)
   + Trên giao diện Fortigate chọn **Dashboard** chọn **+** nhập **Routing** rồi chọn **+** , sau đó chọn **Add Monitor** để tạo bảng **Mornitor Route**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-4.png)
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-5.png)
   + **Dashboard** chọn **Routing Monitor** xem sự xuất hiện của Subnet **aws** trên Fortigate 
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-6.png)


{{% notice info %}}
Lưu ý ở đây : bạn chỉ thấy có 1 route duy nhất trên **Interfaces** của **VPN AWS Tunnel 1** do route mình đang xài dynamic nên cả 2 site Fortigate và AWS sẽ tự động đàm phán để chọn 1 tunnel truyền dữ liệu. Tunnel 2 sẽ ở trạng thái backup khi có downtime ở tunnel 1 trên aws.\
Các bạn có thể tự kiểm tra bằng cách shutdown **interface tunnel 1** nhé.
{{% /notice %}}

5. Kiểm tra ping từ **DC** lên **EC2 Private** và ngược lại
   + Kết nối EC2_Private bằng **System Manager** để ping và kiểm tra **IP**.     
    ![Ping](</images/4.vpnsitetositefortigate/Ping from DC.png>)
    ![Ping](</images/4.vpnsitetositefortigate/ping from AWS.png>)   