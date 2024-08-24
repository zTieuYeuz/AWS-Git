---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

**Tạo IAM ROLE**
   - Trong bước này chúng ta sẽ tiến hành tạo 2 IAM Role. Trong IAM Role này sẽ được gán policy AmazonSSMManagedInstanceCore đây là policy cho phép máy chủ EC2 có thể giao tiếp với Session Manager.\
    
   chèn hinh ảnh mỗi cái xuống dòng là hình ảnh .\
    1. Truy cập vào giao diện quản trị dịch vụ IAM\
    2. Ở thanh điều hướng bên trái, click  **Roles**.\
    3. Click **Create role**.\
    4. Click **AWS service** và click **EC2**.\
        + Click **Next: Permissions**.
    5. Trong ô Search, điền **AmazonSSMManagedInstanceCore**và ấn phím Enter để tìm kiếm policy này.
	  + Click chọn policy **AmazonSSMManagedInstanceCore**.\
	  + Click **Next: Tags.**
    6. Click **Next: Review**.
	7. Đặt tên cho Role là **SSM-Role** ở Role Name  
	  + Click **Create Role**.\
    8. Tiếp theo chúng ta sẽ thực hiện kết nối đến các máy chủ EC2 chúng ta đã tạo bằng **Session Manager**.\
    9. SSM-Role này ta add them policy cho cloudwatch group:

    



