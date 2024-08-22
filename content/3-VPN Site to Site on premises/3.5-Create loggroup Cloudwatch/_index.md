---
title : "Create Cloudwatch"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---

Ở bước này ta tiến hành tạo 2 loggroup trên cloudwatch. 1 Log group để lưu trữ log của vpn aws cho phép chúng ta dễ dàng kiểm tra và biết trạng thái vpn. 1 log group để lưu trữ trạng thái ssm cho phép lưu trữ các command khi nhập trong ec2
## chèn hình ảnh
1. Trong giao diện CloudWatch Logs. Tạo group log cho ssm
- Chọn Log Groups
- Chọn Create log group
- Log group name nhập /aws/ssm/hosts
- Chọn Create
2. Tạo loggroup cho vpn
- Name: nhập vpns2s/log
3. Enable tính năng ssm lưu trữ log về cloudwatch\
Ở bước này bạn bật tính năng cho phép lưu trữ log truy cập và các lệnh thực hiện khi user truy cập vào EC2  về cloudwatch 
Trong giao diện AWS Systems Manager.
-	Chọn Session Manager
-	Chọn tab Preferences
-	Chọn Edit
hình anh
-	Trong Cloudwatch logging
-	Chọn Enable
-	Bỏ chọn Enforce encryption
-	Chọn vpns2s/log
-	Chọn Save





    



