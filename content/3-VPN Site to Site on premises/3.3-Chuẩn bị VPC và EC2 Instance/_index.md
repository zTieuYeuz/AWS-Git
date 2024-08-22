---
title : "Chuẩn bị VPC và EC2 Instance"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

Trong bước này, chúng ta sẽ cần tạo một VPC có 2 subnet public / private. Sau đó tạo 1 EC2 Instance Linux nằm trong public subnet,  1 nằm trong private subnet.

Tổng quan kiến trúc sau khi các bạn hoàn tất bước này sẽ như sau:

![VPC](/images/arc-01.png)

> Chèn hình mỗi mục ở dưới

[Tạo VPC](2.1.1-createvpc/)
- [Tạo Public subnet](2.1.2-createpublicsubnet/)
- [Tạo Private subnet](2.1.3-createprivatesubnet/)
- [Tạo security group](2.1.4-createsecgroup/)
- [Tạo máy chủ Linux public và private ](2.1.5-createec2linux/)

