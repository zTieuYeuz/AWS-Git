---
title: "Create Policy for VPN"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

By default, the Firewall will block all network traffic on all ports. In this section, you will open access policies for both directions of the VPN on both tunnels.\
Note that you still need to refer to the file downloaded from AWS, which contains instructions for configuring this policy.

1. Configure the VPN access policy from **DC** to **AWS** for **tunnel 1**.\
In the Fortigate configuration interface:
   + Select **Policy & Objects**
   + Select **Firewall Policy**
   + Select **Create New**
   + Enter **Name** as **DC TO AWS Tunnel 1**
   + Select **Incoming Interface** as **LAN(Port6)**
   + Select **Outgoing Interface** as **VPN AWS Tunnel1**
   + Select **Source** as **All**
   + Select **Destination** as **All**
   + Select **Service** as **All**
   + Uncheck **NAT**
   + Select **Log Allowed Traffic** as **ALL Sessions** to log all access records
   + Click **OK**
   ![fp](/images/4.vpnsitetositefortigate/Policy-1.png)
   ![fp](/images/4.vpnsitetositefortigate/Policy-3.png)

2. Configure the VPN access policy from **AWS** back to **DC** for **tunnel 1**.\
In the Fortigate configuration interface:
   + Select **Policy & Objects**
   + Select **Firewall Policy**
   + Select **Create New**
   + Enter **Name** as **AWS TO DC Tunnel 1**
   + Select **Incoming Interface** as **VPN AWS Tunnel1**
   + Select **Outgoing Interface** as **LAN(Port6)**
   + Select **Source** as **All**
   + Select **Destination** as **All**
   + Select **Service** as **All**
   + Uncheck **NAT**
   + Select **Log Allowed Traffic** as **ALL Sessions** to log all access records
   + Click **OK**
   ![fp](/images/4.vpnsitetositefortigate/Policy-4.png)
   ![fp](/images/4.vpnsitetositefortigate/Policy-5.png)

3. Configure similar access policies for tunnel 2 in both directions. After completing this, you will have a total of 4 policies.
   ![fp](/images/4.vpnsitetositefortigate/Policy-6.png)