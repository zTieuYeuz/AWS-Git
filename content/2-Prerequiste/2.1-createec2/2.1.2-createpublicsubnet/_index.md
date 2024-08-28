---
title : "Create Public Subnet"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

#### Create Public Subnet

1. Click **Subnets**.
  + Click **Create subnet**.

![VPC](/images/2.prerequisite/003-createsubnet.png)

2. On the **Create subnet** page:
  + In the **VPC ID** field, select **Lab VPC**.
  + In the **Subnet name** field, enter **Public Subnet 1**.
  + In the **Availability Zone** field, select the first Availability Zone.
  + In the **IPv4 CIDR block** field, enter **10.10.1.0/24**.

![VPC](/images/2.prerequisite/004-createsubnet.png)

3. Scroll to the bottom of the page and click **Create subnet**.

4. Select **Public Subnet 1**.
  + Click **Actions**.
  + Click **Edit subnet settings**.

![VPC](/images/2.prerequisite/005-createsubnet.png)

5. Select **Enable auto-assign public IPv4 address**.
  + Click **Save**.

![VPC](/images/2.prerequisite/006-createsubnet.png)

6. Click **Internet Gateways**.
  + Click **Create internet gateway**.

![VPC](/images/2.prerequisite/007-createigw.png)

7. On the **Create internet gateway** page:
  + In the **Name tag** field, enter **Lab IGW**.
  + Click **Create internet gateway**.

![VPC](/images/2.prerequisite/008-createigw.png)

8. After successful creation, click **Actions**.
  + Click **Attach to VPC**.

![VPC](/images/2.prerequisite/009-createigw.png)

9. On the **Attach to VPC** page:
  + In the **Available VPCs** field, select **ASG**.
  + Click **Attach internet gateway**.
  + Verify the successful attachment as shown below.

![VPC](/images/2.prerequisite/010-createigw.png)

10. Next, we will create a custom route table to associate with the **Public Subnet**.
  + Click **Route Tables**.
  + Click **Create route table**.

![VPC](/images/2.prerequisite/011-creatertb.png)

11. On the **Create route table** page:
  + In the **Name** field, enter **Route Table Public**.
  + In the **VPC** field, select **ASG**.
  + Click **Create route table**.

![VPC](/images/2.prerequisite/011-creatertbpublic.png)

12. After successfully creating the route table:
  + Click **Edit routes**.

![VPC](/images/2.prerequisite/012-creatertb.png)

13. On the **Edit routes** page:
  + Click **Add route**.
  + In the **Destination** field, enter **0.0.0.0/0**.
  + In the **Target** field, select **Internet Gateway** and then select the previously created **Lab IGW**.
  + Click **Save changes**.

![VPC](/images/2.prerequisite/013-creatertb.png)

14. Click the **Subnet associations** tab.
  + Click **Edit subnet associations** to associate the custom route table we just created with the **Lab Public Subnet**.

![VPC](/images/2.prerequisite/014-creatertb.png)

15. On the **Edit subnet associations** page:
  + Select **Lab Public Subnet**.
  + Click **Save associations**.

![VPC](/images/2.prerequisite/015-creatertb.png)

16. Verify that the route table has been associated with the **Lab Public Subnet** and that the route to the internet is directed to the **Internet Gateway** as shown below.

![VPC](/images/2.prerequisite/016-creatertb.png)