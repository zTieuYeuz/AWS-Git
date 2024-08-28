---
title : "Create Security Groups"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Create Security Groups

In this step, we will create the security groups used for our instances.

#### Create Security Group for Linux Instance in Public Subnet

1. Access the [VPC service management interface](https://console.aws.amazon.com/vpc)
     + Click **Security Groups**.  
     + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. In the **Security group name** field, input **private_security_group**. 
    + In the **Description** field, input **SG Public for EC2 Public**.
    + In the **VPC** field, select the **VPC ASG** you created for this lab.
    + In the **Inbound rules** section, add 2 rules: **SSH** and **All ICMP - IPv4**.

![SG](/images/2.prerequisite/020-createsg.png)

3. Keep the **Outbound rules** as default, scroll down.
     + Click **Create security group**.

{{%notice tip%}}
You can see that the security group we created for the Linux public instance does not need to open traditional ports for **SSH** like port **22**.
{{%/notice%}}

#### Create Security Group for EC2 Instance in Private Subnet

1. After successfully creating the security group for the Linux instance in the public subnet, click the **Security Groups** link to return to the Security Groups list.

![SG](/images/2.prerequisite/021-createsg.png)

2. Click **Create security group**.

3. In the **Security group name** field, input **Public_security_group**. 
     + In the **Description** field, input **SG for EC2 Private**.
     + In the **VPC** field, select the **ASG** you created for this lab.

![SG](/images/2.prerequisite/022-createsg.png)

4. In the **Inbound rules** section, add 1 rule: **All ICMP - IPv4**. This rule allows ping from EC2 instances in the private subnet.
5. Keep the **Outbound rules** as default, scroll down.
     + Click **Create security group**.

![SG](/images/2.prerequisite/023-createsg.png)

{{%notice tip%}}
For instances in the private subnet, we will use **Session Manager** with a TLS-encrypted connection. Therefore, we can connect through the NAT gateway.
To optimize costs, you can use the **Session Manager** endpoint instead of going out to the internet via the NAT gateway. Here, my lab focuses more on VPN, so if you deploy the endpoint, refer to the lab [Working with Amazon System Manager - Session Manager](https://000058.awsstudygroup.com/vi/).
{{%/notice%}}