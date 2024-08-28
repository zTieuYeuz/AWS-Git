---
title : "Chuẩn bị môi trường On-Premise"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 2.5 </b> "
---


Trong bài thực hành này, chúng ta sẽ xây dựng một mô hình datacenter ở on-premise theo sơ đồ bên dưới:

![FG](/images/DiagramFG.png)

{{% notice info %}}

lưu ý ở bài lab này mình sử dụng v6.4.12 build2060 (GA).Bài lab này có thể triển khai trên nhiều version 6 và 7 

{{% /notice %}}


1.  Cấu hình Interface Wan, Interface Local.
    Trong giao diện cấu hình Fortigate:
    -   Chọn **Network** -> Chọn **Interface WAN1** -> Click **Edit**
    -   Chỗ **Alias**, nhập **Wan Internet**
    -   Chỗ **Address mode** chọn **Manual**
    -   Chỗ **IP/Netmask**, nhập ip ISP cấp **118.107.96.13/24**
    -   Chỗ **Administrative Access** IPv4 chọn **Ping**
    -   Chỗ **Status** chọn **Enabled**
    -   Click **OK**
![FG](/images/2.prerequisite/057-InterfaceFG.png)
![FG](/images/2.prerequisite/058-InterfaceFG.png)
    Tiếp theo ta cấu hình IP Local DC :
    -   Chọn **Network** ->  Chọn **Interface  LAN(Port6)** -> Click **Edit**
    -   Chỗ **Alias**, nhập **LAN**
    -   Chỗ **Address mode** chọn **Manual**
    -   Chỗ **IP/Netmask**, nhập ip local **172.16.4.1/24**
    -   Chỗ **Administrative Access** IPv4 chọn **Ping**
    -   Chỗ **Status** chọn **Enabled**
    -   Click **OK**
![FG](/images/2.prerequisite/059-InterfaceFG.png)
![FG](/images/2.prerequisite/060-InterfaceFG.png)

1.  Cấu hình routing để interface Wan có thể ra ngoài internet.
    -   Chọn **Network** ->  Chọn **Static Routes** -> Click **Create New**
    -   Chỗ **Gateway Address** nhập **118.107.96.1**
    -   Click **OK**
{{% notice info %}}

lưu ý phần này range 118.107.96.0/24 cấu hình trong bài này là dãy địa chỉ ip public do ISP cấp có sẵn đia chỉ IP Gateway.

{{% /notice %}}
![FG](/images/2.prerequisite/062-RouteFG.png)