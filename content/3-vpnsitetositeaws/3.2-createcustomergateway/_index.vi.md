---
title : "Cấu hình Site to Site VPN trên AWS"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

Chúng ta kết nối TTDL On-premise tới Amazon VPC sử dụng VPN phần cứng Fortigate
Để thiết lập kết nối VPN Site to Site, chúng ta sẽ cần tạo và cấu hình Virtual Private Gateway **VPG** và Customer Gateway **CGW**.
- Virtual Private Gateway (VPG) là một trung tâm điều khiển kết nối the virtual private network (VPN) được cài đặt ở đầu AWS.
- A Customer Gateway (CGW) là thành phần đại diện cho thiết bị VPN cứng hoặc mềm được cài đặt ở đầu Khách hàng. Ở đây chính là fortigate.

**VPN tunnel** sẽ được thiết lập ngay sau khi lưu lượng dữ liệu được truyền tải giữa AWS và hệ thống mạng của khách hàng. Trong kết nối đó, ta phải chỉ rõ loại định tuyến sẽ được sử dụng để đảm bảo an toàn cũng như chất lượng về mặt truyền tải dữ liệu.
Do CGW ở phía khách hàng có hỗ trợ Border Gateway Protocol (BGP), thì trong cấu hình VPN connection ta bắt buộc phải đặt định tuyến là dynamic routing.
Amazon VPC cung cấp nhiều loại CGWs, và từng CGW được gán với một VPG nhưng 1 VPG có thể kết hợp với nhiều CGW (many-to-one design). Để hỗ trợ mô hình này thì địa chỉ IP của CGW phải là duy nhất trong một region.
Amazon VPC cũng cung cấp các thông tin cần thiết cho Nhân viên quản trị mạng có thể cấu hình CGW và thiết lập kết nối VPN tới VPG trên AWS. Kết nối VPN luôn bao gồm 2 Internet Protocol Security (IPSec) tunnels để đảm bảo tính sẵn sàng cao của kết nối.


Bên dưới là những đặc điểm quan trọng mà ta cần nắm về VPG, CGW, and VPN:
  - VPG là thành phần đầu cuối của VPN tunnel nằm trên AWS.
  - CGW có thể là thiết bị phần cứng hoặc ứng dụng phần mềm nằm ở đầu Khách hàng trong kết nối VPN tunnel.
  - Bạn phải khởi tạo kết nối VPN tunnel từ CGW tới VPG.
  - VPG hỗ trợ cả dynamic routing (BGP) và static routing.
  - Kết nối VPN luôn có 2 tunnels nhằm đảm bảo tính sẵn sàng cao cho kết nối với VPC từ site Khách hàng.

Bài lab giúp chúng ta học được cách thiết lập một kết nối Site to Site VPN trong AWS. Trong thực tế, giải pháp này khá được nhiều doanh nghiệp sử dụng do ưu điểm Fortigate thông dụng và sử dụng nhiều trong doanh nghiệp, đồng thời rất dễ cấu hình do AWS cung cấp hướng dẫn cho từng loại thiết bị Customer trong 1 file cấu hình. Việc Customer bận tâm duy nhất đó là chuẩn bị đường internet để từ đó tạo đường hầm an toàn bí mật (sử dụng IPSec) kết nối tới AWS thông qua AWS VPN tunnel.
Trong phạm vi bài lab, giả lập rằng chúng ta có Main office ( **VPC ASG** ) và Branch office đặt tại DC On-premises để có sự khác biệt về mặt network. Trên VPC  thực hiện tạo EC2 cho phép SSM ,và 1 PC ở DC. Việc ta cần làm là cấu hình VPN để các địa chỉ Private IP ở 2 đầu có thể ping được lẫn nhau sử dụng VPN Site-to-Site.

Phụ lục
1. [Tạo Virtual Private Gateway](3.1-createvpgw/)
2. [Cấu hình Customer Gateway](3.2-createcustomergw/)
3. [Tạo kết nối VPN](3.3-createvpnconnection/)
