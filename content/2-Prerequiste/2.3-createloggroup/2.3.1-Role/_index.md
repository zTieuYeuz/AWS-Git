---
title : "Role AWS"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 2.3.1 </b> "
---


1. Đăng nhập vào console AWS [IAM](https://console.aws.amazon.com/)
2. Click chọn Role ![role](/images/1.account/r-01.png)
3. Click "create role" ![role](/images/1.account/r-02.png)
4. Click Select trusted ntity
    + click AWS service
    + Service or use case : ec2
    + use case : ec2
![role](/images/1.account/r-03.png)
5. Set permission policies 
    + Click amazonEC2FullAcess
![role](/images/1.account/r-04.png)
6. Review and create 
![role](/images/1.account/r-05.png)

## Chúng ta đã tạo xong role cho AWS


 