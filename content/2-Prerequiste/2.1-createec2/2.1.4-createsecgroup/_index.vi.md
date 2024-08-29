---
title : "Tạo các security group"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Tạo các security group

Trong bước này chúng ta sẽ tiến hành tạo các security group được sử dụng cho các instance của chúng ta. 

#### Tạo security group cho Linux instance nằm trong public subnet 

1. Truy cập [giao diện quản trị dịch vụ VPC](https://console.aws.amazon.com/vpc)
     + Click **Security Group**.  
     + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. Tại mục **Security group name**, điền **public_security_group**. 
    + Tại mục **Description**, điền **SG Public for EC2 Public**.
    + Tại mục **VPC**, chọn lại **VPC ASG** bạn đã tạo cho bài lab này.
    + Trong **Inbound rule** ta add 2 rule **SSH** và **All ICMP - IPV4**

![SG](/images/2.prerequisite/020-createsg.png)

3. Giữ nguyên **Outbound rule**, kéo chuột xuống phía dưới.
     + Click **Create security group**.

{{%notice tip%}}
Các bạn có thể thấy, security group chúng ta tạo sử dụng cho Linux public instance sẽ không cần phải mở các port truyền thống để **ssh** như port **22**.
{{%/notice%}}


#### Tạo security group cho EC2 instance nằm trong private subnet 

1. Sau khi tạo thành công security group cho Linux instance nằm trong public subnet, click vào link Security Groups để quay trở lại danh sách Security groups.

![SG](/images/2.prerequisite/021-createsg.png)

2. Click **Create security group**.

3. Tại mục **Security group name**, điền **private_security_group**. 
     + Tại mục **Description**, điền **SG for EC2 Private**.
     + Tại mục **VPC**, chọn **ASG** bạn đã tạo cho bài lab này.
     + Trong **Inbound rule** ta add 1  **All ICMP - IPV4**. Rule này cho phép ping của EC2 nằm trong private subnet

![SG](/images/2.prerequisite/022-createsg.png)

4. Giữ nguyên **Outbound rule**, kéo chuột xuống phía dưới.
     + Click **Create security group**.

![SG](/images/2.prerequisite/023-createsg.png)

{{%notice tip%}}
Đối với Instance trong private subnet và cả public subnet, chúng ta sẽ dùng  **Session Manager** qua kết nối đã được mã hóa TLS. Vì vậy chúng ta có thể kết nối đến thông qua nat gateway
Để có thể tối ưu hóa chi phí hơn thì bạn có thể dùng endpoint của **Session Manager** thay vì đi ra internet bằng nat gateway. Ở đây bài của mình sẽ forcus nhiều VPN nên nếu các bạn triển khai endpoint thì tham khảo lab [Làm việc với Amazon System Manager - Session Manager](https://000058.awsstudygroup.com/vi/)
{{%/notice%}}

