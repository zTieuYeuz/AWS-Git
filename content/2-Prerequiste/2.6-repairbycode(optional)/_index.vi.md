---
title : "Chuẩn bị môi trường bằng code(Optional)"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 2.6 </b> "
---

Trong phần nãy sẽ hướng dẫn 1 cách để deploy môi trường như phần 2.1 và 2.2 bằng **Infra as Code**. Vì quá trình làm đi làm lại khá nhiều lần nên khi tạo và cấu hình bài lab 2.1 và 2.2 mất rất nhiều thời gian. Chính vì vậy phần này sẽ hướng dẫn 1 số câu lệnh cơ bản để deploy môi trường như 2.1 và 2.2 bằng terraform


{{% notice info %}}

Code này sẽ tạo toàn bộ môi trường như 2.1 và 2.2 [Code ở đây](https://github.com/thangtranit90/InfraAsCode_AWS.git)

{{% /notice %}}


Để có thể sử dụng và viết được terraform bạn cần tìm hiểu cách cài đặt và viết code bằng terraform  :
  - [Cài đặt terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
  - [Cú pháp triển khai cho modules](https://developer.hashicorp.com/terraform/language/modules/syntax)
  - [Sử dụng module built-in có sẵn ](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)
  - [Cài đặt terraform plugin cho VS Code](https://github.com/hashicorp/vscode-terraform)

Để deploy bằng cách sử dụng terraform lên Amazon. Bạn cần cài đặt và cấu hình AWS CLI với các thông tin xác thực **access key** và **Secret key**. Bạn tham khảo 
  - [Cài đặt và làm quen với AWS CLI trên windows ](https://000011.awsstudygroup.com/vi/)


Hướng dẫn sử dụng
1.  Mở folder source INFRAASCODE_AWS trong **VSCODE**
    + Chuyển đường dẫn vào thư mục **Singapore**
    + Tìm tập tin **terraform.tfvars** để khai báo thông tin cần thiết cho khởi tạo tất cả resource ở lab 2.1 và 2.2
      + **region** = "ap-southeast-1".
      + **availability_zone_1** = "ap-southeast-1a"
      + **availability_zone_2** = "ap-southeast-1b"
      + **cidr_block** = "10.10.0.0/16"
      + **public_subnet_ips** = [ "10.10.1.0/24", "10.10.2.0/24" ]
      + **private_subnet_ips** = [ "10.10.100.0/24", "10.10.200.0/24" ]
      + **instance_type** = "t2.micro"
      + **role_name** = "SSM-Role"
    ![tf](/images/2.prerequisite/064-terraform.png)
2.  Mở poweshell trên **VSCODE**. Chuyển đường vào thư mục Singapore
    + Nhập ```terraform init``` để tải về các module,plugin cần thiết cho AWS.
    ![tf](/images/2.prerequisite/065-terraform.png)
    + Sau khi tải xong. Nhập ```terraform plan``` để kiểm tra thông tin các resource sẽ được tạo ra.
    + Tổng cộng có khoảng **26 thông tin** sẽ deploy lên aws
    ![tf](/images/2.prerequisite/066-terraform.png)
    + Sau khi kiểm tra kỹ. Nhập ```terraform apply``` để bắt đầu triển khai resource lên AWS
    + Kiểm tra thông tin thêm 1 lần nữa rồi. Ở **Enter a value** nhập **yes** để triển khai. Nhập **no** nếu không muốn triển khai
    ![tf](/images/2.prerequisite/067-terraform.png)
    + Qúa trình deploy mất khoảng vài phút
    ![tf](/images/2.prerequisite/068-terraform.png)
    ![tf](/images/2.prerequisite/069-terraform.png)



