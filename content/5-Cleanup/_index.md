---
title: "Clean Up Resources"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5 </b> "
---

We will follow these steps to sequentially delete the resources we created in this exercise.
{{% notice info %}}

If you deployed VPC, EC2, ElasticIP, NATGW using Terraform in section 2.6, you can delete them using Terraform without having to delete them manually. Refer to [Step 8](#8).

{{% /notice %}}
1. Delete EC2 instances. Go to the [EC2 service management interface](https://console.aws.amazon.com/ec2/v2/home)
    - Click **Instances**.
    - Select both **EC2_Public** and **EC2_Private** instances.
    - Click **Instance state**.
    - Click **Terminate instance**, then click **Terminate(Delete) instance** to confirm.
        ![clean](/images/5.cleanup/001-clean.png)
    - Click to confirm **Terminate(Delete) instance**
        ![clean](/images/5.cleanup/002-clean.png)

2. NAT Gateway
    - Delete the NAT Gateway and Elastic IP Address. AWS charges for unused EIPs, so you need to check carefully to avoid unwanted costs.
    - Go to the Amazon VPC console.
    - In the left navigation pane, click **NAT Gateway**.
    - Select **NAT Gateway**.
    - Click **Action**.
    - Click Delete **NAT Gateway**.
     ![clean](/images/5.cleanup/003-clean.png)
    - Type delete.
    - Click Delete to confirm the deletion of the NAT Gateway
    ![clean](/images/5.cleanup/004-clean.png)
    
3. Elastic IP Address
    - Continue to delete the **Elastic IP Address**.
    - In the left navigation pane, click **Elastic IP**.
    - Select the Elastic IP Address we created.
    - Click **Actions**
    - Click **Release Elastic IP Address**
    - Click **Release**.
    ![clean](/images/5.cleanup/005-clean.png)
    ![clean](/images/5.cleanup/006-clean.png)

4. Delete VPN Site to Site Connection.
    - In the VPC interface
    - Select **Site-to-Site VPN** connections on the left
    - Select **Actions**
    - Select **Delete VPN connection**
        ![clean](/images/5.cleanup/007-clean.png)
    - Type **delete**
    - Click **Delete** to confirm the deletion of the VPN
        ![clean](/images/5.cleanup/008-clean.png)   
5. Delete Virtual Private Gateway (VPG).
    - In the VPC interface
    - Select **Virtual private gateways**
    - Select **Actions**
    - Select **Detach from VPC**
    - Click **Detach virtual private gateway**
        ![clean](/images/5.cleanup/009-clean.png)  
        ![clean](/images/5.cleanup/010-clean.png)
    - Select **Virtual private gateways**
    - Select **Actions**
    - Select **Delete virtual private gateway**
        ![clean](/images/5.cleanup/011-clean.png)
        ![clean](/images/5.cleanup/012-clean.png)    
6. Delete Customer Gateway (CG).
    - In the VPC interface
    - Select **Customer gateways** on the left
    - Select **Actions**
    - Select **Delete customer gateways**
        ![clean](/images/5.cleanup/013-clean.png)
        ![clean](/images/5.cleanup/014-clean.png)
7. Delete VPC ASG.
    - In the VPC interface
    - Select **ASG**
    - Select **Actions**
    - Select **Delete VPC**
        ![clean](/images/5.cleanup/015-clean.png)

## {#8}
8. Delete resources in steps 1, 2, 3, 7
    - Enter the command ```terraform destroy -auto-approve```. All resources will be deleted after 3 minutes
        ![clean](/images/5.cleanup/016-clean.png)
    - Complete the deletion of all resources
        ![clean](/images/5.cleanup/017-clean.png)