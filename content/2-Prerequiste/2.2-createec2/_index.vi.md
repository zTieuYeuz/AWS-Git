---
title : "Chuẩn bị VPC và EC2"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, chúng ta sẽ cần tạo một VPC có 2 subnet public / private. Sau đó tạo 2 EC2 Instance Linux nằm trong public subnet và private subnet.

Tổng quan kiến trúc sau khi các bạn hoàn tất bước này sẽ như sau:

![VPC](/images/arc-01.png)



### Nội dung
  - [Tạo VPC](2.1.1-createvpc/)
  - [Tạo Public subnet](2.1.2-createpublicsubnet/)
  - [Tạo Private subnet](2.1.3-createprivatesubnet/)
  - [Tạo security group](2.1.4-createsecgroup/)
  - [Tạo 2 máy chủ Linux ở 2 subnet khác nhau](2.1.5-createec2linux/)

