---
title : "Dọn dẹp tài nguyên"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5 </b> "
---


Chúng ta sẽ tiến hành các bước sau để xóa lần lượt các tài nguyên chúng ta đã tạo trong bài thực hành này.
{{% notice info %}}

Nếu bạn triển khai VPC,EC2,ElasticIP,NATGW bằng terraform thì bạn có xóa bằng terraform mà không cần phải xóa bằng tay. Tham khảo [Bước 8](#8)  .

{{% /notice %}}
1.  Xóa các EC2. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home)
    -   Click **Instances**.
    -   Click chọn cả 2 instance **EC2_Public** và **EC2_Private**. 
    -   Click **Instance state**.
    -   Click **Terminate instance**, sau đó click **Terminate(Delete)instance** để xác nhận.
        ![clean](/images/5.cleanup/001-clean.png)
    -   Click xác nhận **Terminate(Delete)instance**
        ![clean](/images/5.cleanup/002-clean.png)



2.  NAT Gateway
    -   Xóa NAT Gateway và Elastic IP Address. AWS sẽ thu tiền cho các EIP lãng phí nên bạn cần kiểm tra kỹ để tránh bị trừ chi phí ngoài ý muốn.
    -   Truy cập trang Amazon VPC console.
    -   Trên thanh điều hướng bên trái , click **NAT Gateway**.
    -   Chọn **NAT Gateway**.
    -   Click **Action**.
    -   Click Delete **NAT Gateway**.
     ![clean](/images/5.cleanup/003-clean.png)
    -   Gõ delete.
    -   Click Delete để xác nhận xóa NAT Gateway
    ![clean](/images/5.cleanup/004-clean.png)
    
3.  Elastic IP Address
    -   Tiếp tục xóa **Elastic IP Address**.
    -   Trên thanh điều hướng bên trái , click **Elastic IP**.
    -   Chọn Elastic IP Address chúng ta đã tạo.
    -   Click **Actions**
    -   Click **Release Elastic IP Address**
    -   Click **Release**.
    ![clean](/images/5.cleanup/005-clean.png)
    ![clean](/images/5.cleanup/006-clean.png)

4.  Xóa VPN Site to Site Connection.
    -   Trong giao diện VPC
    -   Chọn **Site-to-Site VPN** connections ở bên trái
    -   Chọn **Actions**
    -   Chọn **Delete VPN connection** 
        ![clean](/images/5.cleanup/007-clean.png)
    -   Gõ **delete**
    -   Click **Delete** để xác nhận xóa VPN
        ![clean](/images/5.cleanup/008-clean.png)   
5.  Xóa Virtual Private Gateway(VPG).
    -   Trong giao diện VPC
    -   Chọn **Virtual private gateways**
    -   Chọn **Actions**
    -   Chọn **Detach from VPC**
    -   Click **Detach virtual private gateway**
        ![clean](/images/5.cleanup/009-clean.png)  
        ![clean](/images/5.cleanup/010-clean.png)
    -   Chọn **Virtual private gateways**
    -   Chọn **Actions**
    -   Chọn **Delete virtual private gateway**
        ![clean](/images/5.cleanup/011-clean.png)
        ![clean](/images/5.cleanup/012-clean.png)    
6.  Xóa Customer Gateway(CG).
    -   Trong giao diện VPC
    -   Chọn **Customer gateways**  ở bên trái
    -   Chọn **Actions**
    -   Chọn **Delete customer gateways** 
        ![clean](/images/5.cleanup/013-clean.png)
        ![clean](/images/5.cleanup/014-clean.png)
7.  Xóa VPC ASG.
    -   Trong giao diện VPC
    -   Chọn **ASG**
    -   Chọn **Actions**
    -   Chọn **Delete VPC** 
        ![clean](/images/5.cleanup/015-clean.png)

## {#8}
8.  Xóa các resource ở bước 1,2,3,7  
    -   Nhập câu lệnh **terraform destroy -y**