---
title : "Creating a VPN Connection"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3 </b> "
---


---

### Creating a VPN Connection

1. **Access the VPC Console**
    + Select **Site-to-Site VPN Connections**
    + Click **Create VPN Connection**
    ![vpn](/images/3.connect/VPNS2S_1.png)

2. **In the Create VPN Connection Interface**
    + For the Name tag, enter **VPN Connection to DC**
    + Target Gateway Type: Select **Virtual Private Gateway**
    + Virtual Private Gateway: Select **VPN Gateway**
    + Customer Gateway: **Existing**
    + Customer Gateway ID: Select **Customer Gateway**
    + Routing Options: **Dynamic (Requires BGP)**
    + Local IPv4 network CIDR: You can leave this blank or enter the local IP at the DC. In this example, enter **172.16.4.0/24**
    + Remote IPv4 network CIDR: You can leave this blank or enter the AWS CIDR. In this example, it is **10.10.0.0/16**
    ![vpn](/images/3.connect/VPNS2S_2.png)

3. **Continue with the Configuration**
    + Expand **Tunnel 1** options - Optional.
    + Under Tunnel Active – Select **Enable** to send VPN logs to **CloudWatch**
    + Amazon CloudWatch log group: Select **vpns2s/log**
    ![vpn](/images/3.connect/VPNS2S_3.png)
    + Similarly, enable in Tunnel 2 options
    + Click **Create VPN Connection**
    ![vpn](/images/3.connect/VPNS2S_4.png)

4. **Click Create VPN Connection**
    ![vpn](/images/3.connect/VPNS2S_5.png)

5. **Wait approximately 5 minutes for the VPN Connection creation to complete**
    ![vpn](/images/3.connect/VPNS2S_6.png)

6. **Configure Propagation for the Route Tables**
    + In the VPC interface, select **Route Tables**
    + Choose **Route Table - Public**
    + Select **Route Propagation**
    + Click **Edit Route Propagation**
    ![vpn](/images/3.connect/VPN-Route1.png)

7. **In the Edit Route Propagation Interface**
    + Select **Enable**
    + Click **Save**
    ![vpn](/images/3.connect/VPN-Route2.png)

8. **Complete and Verify that Route Propagation has switched to Yes**
    ![vpn](/images/3.connect/VPN-Route3.png)

9. **Similarly, configure Route Propagation for the Private Subnet**
    ![vpn](/images/3.connect/VPN-Route4.png)

---
