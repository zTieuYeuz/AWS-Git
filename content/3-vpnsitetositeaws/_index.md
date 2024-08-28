
---

title : "Configuring Site to Site VPN on AWS"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "

---

We connect the On-premise Data Center to Amazon VPC using a Fortigate hardware VPN. To establish a Site to Site VPN connection, we need to create and configure a Virtual Private Gateway (**VPG**) and a Customer Gateway (**CGW**).
- The Virtual Private Gateway (VPG) is a control center for managing the VPN connection installed at the AWS end.
- A Customer Gateway (CGW) is a component that represents the hardware or software VPN device installed at the customer end, which in this case is Fortigate.

A **VPN tunnel** will be established once data traffic is transmitted between AWS and the customer's network. In this connection, we must specify the type of routing used to ensure the security and quality of data transmission.
If the CGW on the customer side supports Border Gateway Protocol (BGP), dynamic routing must be set in the VPN connection configuration.
Amazon VPC provides various types of CGWs, each associated with a VPG, but a single VPG can be linked with multiple CGWs (many-to-one design). To support this model, the CGW’s IP address must be unique within a region.
Amazon VPC also provides the necessary information for network administrators to configure the CGW and establish a VPN connection to the VPG on AWS. The VPN connection always includes two Internet Protocol Security (IPSec) tunnels to ensure high availability.

Below are the key characteristics of VPG, CGW, and VPN:
  - VPG is the endpoint of the VPN tunnel on AWS.
  - CGW can be a hardware device or a software application located at the customer's end of the VPN tunnel.
  - You must initiate the VPN tunnel connection from the CGW to the VPG.
  - VPG supports both dynamic routing (BGP) and static routing.
  - The VPN connection always has two tunnels to ensure high availability of the connection to the VPC from the customer site.

This lab helps us learn how to set up a Site to Site VPN connection in AWS. In practice, this solution is quite popular among enterprises due to the widespread use and ease of configuration of Fortigate devices, which are commonly used in businesses. AWS also provides configuration guides for each type of Customer Gateway device in a configuration file. The only concern for the customer is to prepare the internet connection, from which a secure and private tunnel (using IPSec) is created to connect to AWS via the AWS VPN tunnel.
Within the scope of this lab, we assume that we have a Main office (**VPC ASG**) and a Branch office located in an On-premises Data Center to differentiate the network. In the VPC, we create an EC2 instance with SSM enabled and a PC in the DC. Our task is to configure the VPN so that the Private IP addresses on both ends can ping each other using the Site-to-Site VPN.

**Appendix:**
1. [Create Virtual Private Gateway](/3-vpnsitetositeaws/3.1-createvirtualprivategateway/_index.md)
2. [Configure Customer Gateway](/content/3-vpnsitetositeaws/3.2-createcustomergateway/_index.md)
3. [Create VPN Connection](/3-vpnsitetositeaws/3.3-createVPN/_index.md)

