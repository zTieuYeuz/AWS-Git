---
title : "Tạo Private subnet"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

#### Tạo Private subnet

1. Tại giao diện VPC. Click **Subnets**.
     + Click **Create subnet**.

![VPC](/images/2.prerequisite/017-createsubnet.png)

1. Tại trang **Create subnet**.
     + Tại mục **VPC ID** click chọn **ASG**.
     + Tại mục **Subnet name** điền **Private Subnet 1**.
     + Tại mục **Availability Zone** chọn Availability zone đầu tiên.
     + Tại mục **IPv4 CIRD block** điền **10.10.100.0/24**.
  ![VPC](/images/2.prerequisite/018-createprivatesubnet1.png)

1. Kéo xuống cuối trang , click **Create subnet**.
  ![VPC](/images/2.prerequisite/017-createsubnet3.png)
1. Lập lại các bước trên để tạo cho **Private Subnet 2**
    ![VPC](/images/2.prerequisite/018-createprivatesubnet2.png)

2. Tiếp theo chúng ta sẽ tạo một custom route table để gán vào **Private Subnet**.
     + Click **Route Tables**.
     + Click **Create route table**.
  ![VPC](/images/2.prerequisite/018-createrouteprivate0.png)
1. Tại trang **Create route table**.
     + Tại mục **Name**, điền **Route Table Private**.
     + Tại mục **VPC**, chọn **ASG**.
     + Click **Create route table**.
  ![VPC](/images/2.prerequisite/018-createrouteprivate1.png)
1. Trong giao diện Route table - Private
     + Chọn Subnet Associations
     + Chọn Edit subnet associations
  ![VPC](/images/2.prerequisite/018-createrouteprivate2.png)
1. Trong giao diện Edit subnet associations
     + Chọn 2 private subnet
     + Chọn Save associations
  ![VPC](/images/2.prerequisite/018-createprivatesubnet3.png)
  





Bước tiếp theo chúng ta sẽ tạo các nat gateway để cho phép các ec2 ở private subnet được phép giao tiếp với internet.

#### Tạo NAT Gateway

Trong bước này chúng ta sẽ tiến hành tạo **nat gateway** để cho phép các ec2 trong **private subnet** được ra ngoài internet. 

1. Truy cập [giao diện quản trị VPC](https://ap-southeast-1.console.aws.amazon.com/vpcconsole/).
   Trong giao diện NAT gateway
      + Name, nhập **My Natgw**
      + Subnet, chọn **Public subnet 2**
      + Connectivity type, chọn **Public**
      + **Elastic IP allocation ID**, Click **Allocate Elastic IP** để tạo Elastic IP.
      + Click **Create Nat Gateway**
    ![natgw](/images/2.prerequisite/052-natgw.png)
2.  Thành công tạo NAT gateway
    ![natgw](/images/2.prerequisite/053-natgw.png)


3. Trong giao diện Route table - Private
      + Chọn Routes
      + Chọn Edit routes
   ![natgw](/images/2.prerequisite/054-natgw.png)
4.  Trong giao diện Edit routes
+ Chọn Add route
      + Chọn Destination: 0.0.0.0/0
      + Target: NAT Gateway
      + Chọn Save changes
   ![natgw](/images/2.prerequisite/055-natgw.png)
5. Kiểm tra lại Routes
   ![natgw](/images/2.prerequisite/056-natgw.png)



