---
title : "Prepare On-Premise Environment"
date : "`r Sys.Date()`"
weight : 5 
chapter : false
pre : " <b> 2.5 </b> "
---

In this exercise, we will build an on-premise datacenter model according to the diagram below:

![FG](/images/DiagramFG.png)

{{% notice info %}}

Note that in this lab, I am using version 6.4.12 build 2060 (GA). This lab can be deployed on many versions 6 and 7.

{{% /notice %}}

1. Configure WAN Interface and Local Interface.
    In the Fortigate configuration interface:
    -   Select **Network** -> Select **Interface WAN1** -> Click **Edit**.
    -   In the **Alias** field, input **Wan Internet**.
    -   In the **Address mode** field, select **Manual**.
    -   In the **IP/Netmask** field, input the ISP-provided IP **118.107.96.13/24**.
    -   In the **Administrative Access** IPv4 field, select **Ping**.
    -   In the **Status** field, select **Enabled**.
    -   Click **OK**.
![FG](/images/2.prerequisite/057-InterfaceFG.png)
![FG](/images/2.prerequisite/058-InterfaceFG.png)
    Next, configure the Local DC IP:
    -   Select **Network** -> Select **Interface LAN (Port6)** -> Click **Edit**.
    -   In the **Alias** field, input **LAN**.
    -   In the **Address mode** field, select **Manual**.
    -   In the **IP/Netmask** field, input the local IP **172.16.4.1/24**.
    -   In the **Administrative Access** IPv4 field, select **Ping**.
    -   In the **Status** field, select **Enabled**.
    -   Click **OK**.
![FG](/images/2.prerequisite/059-InterfaceFG.png)
![FG](/images/2.prerequisite/060-InterfaceFG.png)

2. Configure routing so that the WAN interface can access the internet.
    -   Select **Network** -> Select **Static Routes** -> Click **Create New**.
    -   In the **Gateway Address** field, input **118.107.96.1**.
    -   Click **OK**.
{{% notice info %}}

Note that the range 118.107.96.0/24 configured in this lab is a public IP address range provided by the ISP, which includes the IP Gateway address.

{{% /notice %}}
![FG](/images/2.prerequisite/062-RouteFG.png)