---
title : "Dọn dẹp tài nguyên"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.8.2 </b> "
---

1. Terminate EC2 instance.
    + Truy cập Amazon EC2 console tại địa chỉ EC2.
    + Trên thanh điều hướng bên trái, chọn Intances
    + Chọn tất cả EC2 Instance liên quan tới bài lab.
    + Chọn Instance state
    + Chọn Terminate instance
## chèn hình
2. Xác nhận terminate.
## chen hình
- Xóa NAT Gateway, Elastic IP Address
    + Xóa NAT Gateway và Elastic IP Address. AWS sẽ thu tiền cho các EIP lãng phí nên bạn cần kiểm tra kỹ để tránh bị trừ chi phí ngoài ý muốn.
    + Truy cập trang Amazon VPC console tại địa chỉ VPC
    + Trên thanh điều hướng bên trái , click NAT Gateway.
    + Chọn NAT Gateway.
    + Click Action.
    + Click Delete NAT Gateway
    ## chèn hình
    + Gõ delete.
    + Click Delete để xác nhận xóa NAT Gateway
    ## chèn hình
- Xóa  Elastic IP Address.
    + •	Tiếp tục xóa Elastic IP Address.
    + Truy cập trang Amazon VPC console tại địa chỉ https://console.aws.amazon.com/vpc/
    + Trên thanh điều hướng bên trái , click Elastic IP.
    + Chọn Elastic IP Address chúng ta đã tạo.
    + Click Action.
    + Click Release Elastic IP Address
    + Click Release.
    ## chèn hình















