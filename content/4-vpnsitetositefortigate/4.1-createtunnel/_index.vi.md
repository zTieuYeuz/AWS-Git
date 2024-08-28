*---
title : "Tao Tunnel IPSEC"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---



Trong bài thực hành này, chúng ta tạo và cấu hình IPSEC trên thiết bị **Fortigate** dựa vào [file Configuration](#download-configuration) được download từ Amazon.Chi tiết cấu hình như sau:

1.	Truy cập vào VPC
    -   Chọn **Site-to-Site VPN Connection**
    -   Chọn VPN Connection đã tạo
    -   Chọn **Download Configuration**
    ![vpnfg](/images/4.vpnsitetositefortigate/001-vpnfg.png)


2.	Trong hộp thoại **Download Configuration**, lựa chọn appliance phù hợp với bạn: Trong bài thực hành này, chúng ta sẽ sử dụng **Fortigate**.
    -   **Vendor**: Chọn **Fortinet**
    -   **Platform**: Chọn **Fortigate 40+series**
    -   **Software**: Chọn **FortiOS 6.4.4+ (GUI)**
    -   **IKE version**: Chọn **ikev1**
    -   Chọn **Download**.
    ![vpnfg](/images/4.vpnsitetositefortigate/002-vpnfg.png)
{{% notice info %}}

Lưu ý ở bước này do để các bạn nắm cơ bản phần cấu hình trước để dàng xử lý sự cố nên ở đây mình chọn ikev1. Nếu triển khai thực tế nên sử dụng **ikev2**. Ưu điểm lớn nhất của ikev2 là quá trình đàm phán bắt tay giữa 2 site sẽ nhanh hơn và hỗ trợ nhiều thuật toán bảo mật hơn.

{{% /notice %}}




##### download-configuration
3.	Lưu thông tin file cấu hình vào thư mục :
    -   Sau đó dựa vào cấu hình được cung cấp, bạn cấu hình các thông tin này cho thiết bị của mình.
    ![vpnfg](/images/4.vpnsitetositefortigate/003-vpnfg.png)

4.	Tại giao diện Fortigate tạo tunnel 1 VPN:
    -   Chọn **VPN** -> IPsec Wizard
    -   **Template type** chọn **Custom**
    -   **Name** nhập **VPN AWS Tunnel 1**
    -   Chọn **Next**
    ![vpnfg](/images/4.vpnsitetositefortigate/004-vpnfg.png)

5.	Tại giao diện **New VPN Tunnel** bạn tạo tunnel 1 cho VPN :
    #### Phase 1
    -   **IP address** nhập **18.143.226.251**
    -	**Interface** chọn **Wan Internet(Wan 1)**
    -	**NAT Traversal** chọn **Disable**
    -	**Pre-shared Key** nhập thông số như trong file **DS6CXQf8YMvA0E4wRo4uDGRtcVofGiad**
    -	**Phase 1 Proposal** bạn xóa hết các dòng trước đó và cấu hình **Encryption** chọn **AES128**, **Authentication** chọn **SHA1** 
    -	**Diffie-Hellman Groups** bỏ chọn **14,5** . Chỉ chọn **2**
    -	**Key Lifetime (seconds)** nhập **28800**
    ![vpnfg](/images/4.vpnsitetositefortigate/005-vpnfg.png)
    #### Phase 2
    -	**Phase 2 Selectors** click **+**
    -	**Phase 2 Proposal** xóa toàn bộ các dòng trước đó và cấu hình **Encryption** chọn **AES128**, **Authentication** chọn **SHA1**
    -	**Diffie-Hellman Groups** bỏ chọn **14,5** . Chỉ chọn **2** 
    -	Chọn Auto-negotiate
    -	**Seconds** nhập **3600**
    -	Chọn **OK** để tạo
    ![vpnfg](/images/4.vpnsitetositefortigate/006-vpnfg.png)
    ![vpnfg](/images/4.vpnsitetositefortigate/007-vpnfg.png)
6.	Tại giao diện **New VPN Tunnel** bạn làm tương tự cho **tunnel 2** như **tunnel 1**:
    -   Mở lại **file config** đã download trước tìm và mở phần thông số cho tunnel 2
        ![vpnfg](/images/4.vpnsitetositefortigate/008-vpnfg.png)
    -   Cấu hình **Phase1** **Phase2** tương tự như **Tunnel 1**
    ![vpnfg](/images/4.vpnsitetositefortigate/009-vpnfg.png)
    ![vpnfg](/images/4.vpnsitetositefortigate/010-vpnfg.png)
    ![vpnfg](/images/4.vpnsitetositefortigate/011-vpnfg.png)
7.  Kiểm tra lại giao diện ta có tổng cộng **2 tunnel** đã cấu hình
    ![vpnfg](/images/4.vpnsitetositefortigate/012-vpnfg.png)*