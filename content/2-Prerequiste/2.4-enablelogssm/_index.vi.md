---
title : "Quản lý session logs của SSM với CloudWatch Logs"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 2.4 </b> "
---



Trong bước này chúng ta sẽ tiến hành bật tính năng **CloudWatch** trong **SSM** để cho phép lưu trữ log truy cập và các lệnh thực hiện khi user truy cập vào EC2 sẽ được đẩy về **CloudWatch** 


1. Trong giao diện [AWS Systems Manager](https://ap-southeast-1.console.aws.amazon.com/systems-manager)
   + Chọn **Session Manager**
   + Chọn **tab Preferences**
   + Chọn **Edit**
   
   ![enablessm](/images/2.prerequisite/049-SSM.png)
   
   + Trong Cloudwatch logging
   + Chọn **Enable**
   + Bỏ chọn **Enforce encryption**
   + Chọn **vpns2s/log**
   + Chọn **Save**
   ![enablessm](/images/2.prerequisite/050-SSM.png)
   ![enablessm](/images/2.prerequisite/051-SSM.png)


