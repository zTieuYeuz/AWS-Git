---
title : "Tạo CloudWatch Log Groups"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.3 </b> "
---

### Tạo CloudWatch LogGroup

Trong bước này chúng ta sẽ tiến hành tạo 2 **Cloud Watch Log Group**. Mục đích :
    + Lưu trữ và phân loại log của vpn aws cho phép chúng ta dễ dàng kiểm tra và biết trạng thái vpn. 
    + lưu trữ và phân loại log các dòng lệnh đã sử dụng khi dùng ssm truy cập vào ec2.
 
2. Truy cập vào [giao diện quản trị dịch vụ Cloud Watch](https://ap-southeast-1.console.aws.amazon.com/cloudwatch/)
3. Tạo **Log Groups** cho ssm:
   + Chọn **Log Groups**
   + Chọn **Create log group**
   + Log group name nhập ```/aws/ssm/hosts```
   + Chọn **Create**
   ![Loggroup](/images/2.prerequisite/046-LogGroup.png)
   ![Loggroup](/images/2.prerequisite/047-LogGroup.png)

4. Tương tự tạo **Log Groups** cho VPN:
   + **Name** nhập ```vpns2s/log```
   ![Loggroup](/images/2.prerequisite/048-LogGroup.png)

