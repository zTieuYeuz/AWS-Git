---
title : "Tạo Policy cho VPN"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

Mặc định Firewall sẽ chặn tất cả lưu lương mạng ở tất cả các cổng. Ở phần này bạn sẽ mở chính sách truy cập ở cả 2 chiều của VPN trên cả 2 tunnel.\
Lưu ý ở bước các bạn vẫn phải dựa vào file đã download từ aws. Trong đó có trong nội dung hướng dẫn cấu hình policy này
1. Cấu hình mở chính sách truy cập VPN từ **DC** lên **aws** cho **tunnel 1**.\
Trong giao diện cấu hình Fortigate:
      + Chọn **Policy & Objects**
      + Chọn **Firewall Policy**
      + Chọn **Create New**
      + **Name** nhập **DC TO AWS Tunnel 1**
      + **Incoming Interface** chọn **LAN(Port6)**
      + **Outgoing Interface** chọn **VPN AWS Tunnel1**
      + **Source** chọn **All**
      + **Destination** chọn **All**
      + **Service** chọn **All**
      + **NAT** chọn uncheck**
      + Log Allowed Traffic chọn **ALL Sessions**. Để có ghi nhận lại tất cả nhật ký truy cập
      + Chọn **OK**
      ![fp](/images/4.vpnsitetositefortigate/Policy-1.png)
      ![fp](/images/4.vpnsitetositefortigate/Policy-3.png)
2. Cấu hình mở chính sách truy cập VPN từ **AWS** về lại **DC** cho **tunnel 1**.\
      Trong giao diện cấu hình Fortigate:
     + Chọn **Policy & Objects**
     + Chọn **Firewall Policy**
     + Chọn **Create New**
     + **Name** nhập **AWS TO DC Tunnel 1**
     + **Incoming Interface** chọn **VPN AWS Tunnel1**
     + **Outgoing Interface** chọn **LAN(Port6)**
     + **Source** chọn **All**
     + **Destination** chọn **All**
     + **Service** chọn **All**
     + **NAT** chọn **uncheck**
     + **Log Allowed Traffic** chọn **ALL Sessions**. Để có ghi nhận lại tất cả nhật ký truy cập
     + Chọn **OK**
      ![fp](/images/4.vpnsitetositefortigate/Policy-4.png)
      ![fp](/images/4.vpnsitetositefortigate/Policy-5.png)
3. Cấu hình mở chính sách truy cập tương tự cho tunnel 2 ở 2 chiều. Ở phần này các bạn tự cấu hình tương tự sau khi xong bạn sẽ có tổng cộng 4 policy
      ![fp](/images/4.vpnsitetositefortigate/Policy-6.png)