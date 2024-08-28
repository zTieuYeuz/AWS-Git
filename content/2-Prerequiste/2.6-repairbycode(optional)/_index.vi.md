---
title : "Chuẩn bị môi trường bằng code(Optional)"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 2.6 </b> "
---

Trong phần nãy sẽ hướng dẫn 1 cách để deploy môi trường như phần 2.1 và 2.2 bằng **Infra as Code**. Vì quá trình làm đi làm lại khá nhiều lần nên khi tạo và cấu hình được như phần 2.1 mất rất nhiều thời gian. Chính vì vậy phần này sẽ hướng dẫn 1 số câu lệnh cơ bản để deploy môi trường như 2.1 bằng terraform


{{% notice info %}}

Code này sẽ tạo toàn bộ môi trường như 2.1. [Link down source code]()

{{% /notice %}}


Để tìm hiểu cách cài đặt và viết code bằng terraform  :
  - [Cài đặt terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
  - [Cú pháp triển khai cho modules](https://developer.hashicorp.com/terraform/language/modules/syntax)
  - [Sử dụng module built-in có sẵn ](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)
  - [Cài đặt terraform plugin cho VS Code](https://github.com/hashicorp/vscode-terraform)

Để deploy bằng cách sử dụng terraform lên Amazon. Bạn tham khảo  :
  - [Cài đặt và làm quen với AWS CLI trên windows ](https://000011.awsstudygroup.com/vi/)
  - [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)

1.  Tạo cặp key pair. Mục đích sử dụng trong lúc tạo code để ssh vào các EC2

    ```sh
        ssh-keygen -t rsa -b 4096 -C "your_email@gmail.com"


