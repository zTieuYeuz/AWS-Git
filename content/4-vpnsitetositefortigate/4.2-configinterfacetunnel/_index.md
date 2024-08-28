---
title: "Configure Interface Tunnel 1 & 2 on Fortigate"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

In the Fortigate configuration interface:
1. Configure Interface Tunnel 1
   + In **Network** -> Interface WAN1 -> Click **+** -> Select **VPN AWS Tunnel 1** -> Click **Edit**
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface1.png)
   + Enter **IP** as **169.254.52.6**
   + Enter **Remote IP/Netmask** as **169.254.52.5/30**
   + Select **Administrative Access** as **Ping**
   + Select **Status** as **Enable**
   + Click **OK**
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface2.png)

2. Configure Interface Tunnel 2
   + Enter **IP** as **169.254.52.6**
   + Enter **Remote IP/Netmask** as **169.254.52.5/30**
   + Select **Administrative Access** as **Ping**
   + Select **Status** as **Enable**
   + Click **OK**
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface3.png)

3. Verify the **2 interface tunnels** created
![fg](/images/4.vpnsitetositefortigate/FG-VPN-Interface4.png)