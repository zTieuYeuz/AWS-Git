---
title : "Các bước chuẩn bị"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}

Trước khi bắt đầu cấu hình VPN với AWS và Fortinet. Bạn nên chuẩn bị cho mình 1 chút kiến thức về giao thức định tuyến tĩnh và động. Bạn tham khảo thêm giới thiệu sơ về Dynamic Routing **BGP** sẽ sử dụng trong bài lab này ở phần 4

{{% /notice %}}

{{% notice info %}}

Để thực hiện được bài lab này bạn cần phải nghiên cứu thêm về tường lửa Fortigate. Có thể dùng ảo hóa firewall này trên vmware với license 14 ngày để làm lab. Còn đây mình dùng phần cứng Fortigate 100F( Version v6.4.12 build2060 (GA))

{{% /notice %}}

{{% notice info %}}

Bạn cần tạo sẵn 2 Linux instance thuộc public subnet và private subnet để thực hiện bài thực hành này.

{{% /notice %}}


Để tìm hiểu cách tạo các EC2 instance và VPC với public/private subnet các bạn có thể tham khảo bài lab :
  - [Giới thiệu về Amazon EC2](https://000004.awsstudygroup.com/vi/)
  - [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)

Để tìm hiểu cách tạo IAM role gán quyền ssm,cloudwatch các bạn có thể tham khảo bài lab:
  - [AWS CloudWatch Workshop](https://000008.awsstudygroup.com/)
  - [Làm việc với Amazon System Manager - Session Manager](https://000058.awsstudygroup.com/vi/)

Để tìm hiểu giao thức định tuyến có thể tham khảo:
  - [Giao thức Border Gateway Protocol(BGP)](https://aws.amazon.com/what-is/border-gateway-protocol/)

Phụ lục
1. [Chuẩn bị VPC và EC2 Instance](2.1-createec2/)
2. [Tạo IAM Role](2.2-createiamrole/)
3. [Tạo loggroup Cloudwatch](2.3-createloggroup/)
4. [Bật tính năng ssm lưu trữ log về cloudwatch](2.4-enablelogssm/)
5. [Chuẩn bị thiết bị Fortigate](2.5-fortigate/)