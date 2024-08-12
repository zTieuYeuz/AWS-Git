---
title : "MFA"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 7.1.1 </b> "
---

#### MFA Cho AWS
1. Đăng nhập vào console AWS [IAM](https://console.aws.amazon.com/)
    + click vào IAM ![MFA](/images/1.account/001-taikhoan.png)
    + Click vào MFA trong dashboard ![MFA](/images/1.account/MFA-taikhoan2.png)
2. Điền thông tin của MFA cho tài khoản
    + Điền divice name và chọn authenticator app ![MFA](/images/1.account/MFA-taikhoan3.png)
    + Show mã QR ![MFA](/images/1.account/MFA-taikhoan4.png)
3. Tải app cho MFA
    + Googgle authenticator
    + Microsoft authenticator
    + authy
4. Quét mã QR và điền mã
    + điền 2 lần mã vào ô phía dưới ![MFA](/images/1.account/MFA-taikhoan5.png)
5. Sau khi AWS đã xác nhận xong chúng ta quay về đăng nhập
    + yêu cầu mã MFA ![MFA](/images/1.account/MFA-taikhoan6.png)
### Từ đây khi đăng nhập AWS ta đã được bảo vệ 