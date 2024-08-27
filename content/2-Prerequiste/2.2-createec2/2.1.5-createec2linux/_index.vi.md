---
title : "Tạo EC2 ở Private Subnet và Public Subnet"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

1. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home)
  + Click **Instances**.
  + Click **Launch instances**.
  
![EC2](/images/2.prerequisite/027-createec2.png)

2. Tại trang **Step 1: Choose an Amazon Machine Image (AMI)**.
  + Click **Select** để lựa chọn AMI **Amazon Linux 2 AMI**.
  
![EC2](/images/2.prerequisite/028-createec2.png)

3. Kéo xuống dưới phần:
 + Click chọn Instance type **t2.micro**.
 + Tại mục **Network** chọn **ASG**.
 + Tại mục **Subnet** chọn **Public Subnet 1**
 + Tại mục **Auto-assign Public IP** chọn **Enable**
 + Chọn **Select an existing security group**
 + Chọn security group **public_security_group**.
 
![EC2](/images/2.prerequisite/029-createec2.png)
![EC2](/images/2.prerequisite/030-createec2.png)


4. Tại Phần **Advanced Details**.
  + Mục **IAM instance profile** chọn **SSM-Role**
  + Chọn **Lauch instance**

![EC2](/images/2.prerequisite/031-createec2.png)

5. Lập lại tương tự từ bước 2-4. Tạo 1 EC2. Nhưng lưu ý 1 vài điểm 
   + Tại mục **Subnet** chọn **Private Subnet 2**
   + Tại mục **Auto-assign Public IP** chọn **Disable**
   + Chọn security group **private_security_group**
   + Còn lại làm như bước 2-4
   + Sau khi tạo xong ta có kết quả
![VPC](/images/2.prerequisite/034-createec2.png)