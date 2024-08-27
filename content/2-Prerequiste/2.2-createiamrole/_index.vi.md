---
title : "Tạo IAM Role"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Tạo IAM Role

Trong bước này chúng ta sẽ tiến hành tạo IAM Role. Trong IAM Role này sẽ được gán policy **AmazonSSMManagedInstanceCore** và **CloudwatchLogsFullAccess**, đây là policy cho phép máy chủ EC2 có thể giao tiếp với Session Manager và Cloud Watch log.

1. Truy cập vào [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/)
2. Ở thanh điều hướng bên trái, chọn  **Roles**. Chọn  **Create role**.

![role1](/images/2.prerequisite/039-iamrole.png)


3. Click **AWS service** và click **EC2**. 
  + Click **Next: Permissions**.  

![role1](/images/2.prerequisite/040-iamrole.png)

4. Trong thanh tìm kiếm, 
  + Điền **AmazonSSMManagedInstanceCore** và ấn phím Enter để tìm kiếm policy này.
  + Chọn policy **AmazonSSMManagedInstanceCore**.
  + Tiếp tục điền **CloudwatchLogsFullAccess** và ấn phím Enter để tìm kiếm policy này.
  + Chọn policy **CloudwatchLogsFullAccess**
  + Click **Next: Tags.**

![addpolicy](/images/2.prerequisite/041-iamrole.png)
![addpolicy](/images/2.prerequisite/042-iamrole.png)

5. Click **Next: Review**.
6. Đặt tên cho Role là **SSM-Role** ở Role Name  
  + Click **Create Role**

![NameRole](/images/2.prerequisite/043-iamrole.png)

7. Tiếp theo chúng ta sẽ gán role này vào các ec2 public và private. Truy cập vào [giao diện quản trị dịch vụ máy chủ ảo](https://ap-southeast-1.console.aws.amazon.com/ec2).
  + Click **Instances**
  + Check **EC2_Private**
  + Click **Action** -> Click **Security**
  + Click **Change security groups**

![Attachrole](/images/2.prerequisite/044-iamrole.png)

8. Chọn **SSM-Role** vừa tạo.
   + Click **Update IAM **role**

![Attachrole](/images/2.prerequisite/045-iamrole.png)

