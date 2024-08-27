---
title : "Các bước chuẩn bị"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2 </b> "
---

{{% notice info %}}

Để cần thực hiện lab này bạn cần phải nghiên cứu thêm về tường lửa Fortigate. Có thể dùng ảo hóa trên vmware ( license 14 ngày) để test lab. Còn ở đây mình dùng Fortigate 100F( Version ……)
Bạn cần tạo sẵn 2 Linux instance thuộc public subnet và private subnet để thực hiện bài thực hành này.
Các bạn cần trang bị 1 số kiến thức liên quan đến routing dynamic, VPC,Cloudwatch,SSM
{{% /notice %}}

Để tìm hiểu cách tạo các EC2 instance và VPC với public/private subnet các bạn có thể tham khảo bài lab :
  - [Giới thiệu về Amazon EC2](https://000004.awsstudygroup.com/vi/)
  - [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)

Để tìm hiểu cách tạo IAM role gán quyền ssm,cloudwatch các bạn có thể tham khảo bài lab:
  - [AWS CloudWatch Workshop](https://000008.awsstudygroup.com/)
  - [Làm việc với Amazon System Manager - Session Manager](https://000058.awsstudygroup.com/vi/)

Phụ lục
1. [Chuẩn bị VPC và EC2 Instance](2.1-createvpc_ec2/)
2. [Tạo IAM Role](2.2-createiamrole/)
3. [Tạo loggroup Cloudwatch](2.3-createloggroup/)
4. [Bật tính năng ssm lưu trữ log về cloudwatch](2.4-enablelogssm/)
5. [Chuẩn bị thiết bị Fortigate](2.5-fortigate/)