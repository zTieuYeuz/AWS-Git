---
title : "Create EC2 in Private Subnet and Public Subnet"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

1. Access the [EC2 service management interface](https://console.aws.amazon.com/ec2/v2/home)
  + Click **Instances**.
  + Click **Launch instances**.
  
![EC2](/images/2.prerequisite/027-createec2.png)

2. On the **Step 1: Choose an Amazon Machine Image (AMI)** page:
  + Click **Select** to choose the **Amazon Linux 2 AMI**.
  
![EC2](/images/2.prerequisite/028-createec2.png)

3. Scroll down to:
 + Select the instance type **t2.micro**.
 + In the **Network** field, select **ASG**.
 + In the **Subnet** field, select **Public Subnet 1**.
 + In the **Auto-assign Public IP** field, select **Enable**.
 + Select **Select an existing security group**.
 + Select the security group **public_security_group**.
 
![EC2](/images/2.prerequisite/029-createec2.png)
![EC2](/images/2.prerequisite/030-createec2.png)

4. In the **Advanced Details** section:
  + In the **IAM instance profile** field, select **SSM-Role**.
  + Click **Launch instance**.

![EC2](/images/2.prerequisite/031-createec2.png)

5. Repeat steps 2-4 to create another EC2 instance, but note the following changes:
   + In the **Subnet** field, select **Private Subnet 2**.
   + In the **Auto-assign Public IP** field, select **Disable**.
   + Select the security group **private_security_group**.
   + Follow the rest of the steps as in steps 2-4.
   + After creation, you should see the following result:
![VPC](/images/2.prerequisite/034-createec2.png)