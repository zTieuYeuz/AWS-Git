---
title: "Check VPN Status"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.5 </b> "
---

1. Access CloudWatch logs to view logs for phase 1 and phase 2 of the VPN
   [In the CloudWatch interface](https://ap-southeast-1.console.aws.amazon.com/cloudwatch/home)
   + Select **Log groups**, choose **vpns2s/log**, each **Log streams** represents a tunnel.
   + If the status of **ike_phase1_state** and **ike_phase2_state** are both **established**, then the VPN is **up**. If not, use the logs here to diagnose the issue.
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-0.png)
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-01.png)

2. To ensure, check the **tunnel** status on both site interfaces:
   + VPN tunnel status up on **Fortigate**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-1.png)
   + VPN status on **AWS**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-2.png)
3. Check the **routing table**
   + The **routing table** on **AWS** will automatically show the **172.16.4.0/24** subnet of the **DC**
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-3.png)
   + On the Fortigate interface, select **Dashboard**, click **+**, enter **Routing**, then click **+**, and select **Add Monitor** to create a **Monitor Route** table
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-4.png)
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-5.png)
   + In the **Dashboard**, select **Routing Monitor** to see the appearance of the **AWS** subnet on Fortigate
      ![check](/images/4.vpnsitetositefortigate/Monitoring%20VPN-6.png)

{{% notice info %}}
Note: You will only see one route on the **Interfaces** of **VPN AWS Tunnel 1** because the route is dynamic, so both Fortigate and AWS sites will automatically negotiate to select one tunnel for data transmission. Tunnel 2 will be in backup state when there is downtime on tunnel 1 on AWS.\
You can test this by shutting down **interface tunnel 1**.
{{% /notice %}}

5. Check ping from **DC** to **EC2 Private** and vice versa
   + Connect to EC2_Private using **System Manager** to ping and check the **IP**.
    ![Ping](</images/4.vpnsitetositefortigate/Ping from DC.png>)
    ![Ping](</images/4.vpnsitetositefortigate/ping from AWS.png>)