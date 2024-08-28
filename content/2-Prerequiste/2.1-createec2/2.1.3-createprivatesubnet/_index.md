---
title : "Create Private Subnet"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

#### Create Private Subnet

1. In the VPC interface, click **Subnets**.
     + Click **Create subnet**.

![VPC](/images/2.prerequisite/017-createsubnet.png)

2. On the **Create subnet** page:
     + In the **VPC ID** field, select **ASG**.
     + In the **Subnet name** field, enter **Private Subnet 1**.
     + In the **Availability Zone** field, select the first Availability Zone.
     + In the **IPv4 CIDR block** field, enter **10.10.100.0/24**.
  ![VPC](/images/2.prerequisite/018-createprivatesubnet1.png)

3. Scroll to the bottom of the page and click **Create subnet**.
  ![VPC](/images/2.prerequisite/017-createsubnet3.png)
4. Repeat the above steps to create **Private Subnet 2**.
    ![VPC](/images/2.prerequisite/018-createprivatesubnet2.png)

5. Next, we will create a custom route table to associate with the **Private Subnet**.
     + Click **Route Tables**.
     + Click **Create route table**.
  ![VPC](/images/2.prerequisite/018-createrouteprivate0.png)
6. On the **Create route table** page:
     + In the **Name** field, enter **Route Table Private**.
     + In the **VPC** field, select **ASG**.
     + Click **Create route table**.
  ![VPC](/images/2.prerequisite/018-createrouteprivate1.png)
7. In the Route table - Private interface:
     + Select **Subnet Associations**.
     + Select **Edit subnet associations**.
  ![VPC](/images/2.prerequisite/018-createrouteprivate2.png)
8. In the **Edit subnet associations** interface:
     + Select the 2 private subnets.
     + Click **Save associations**.
  ![VPC](/images/2.prerequisite/018-createprivatesubnet3.png)

The next step is to create NAT gateways to allow EC2 instances in the private subnet to communicate with the internet.

#### Create NAT Gateway

In this step, we will create a **NAT gateway** to allow EC2 instances in the **private subnet** to access the internet.

1. Access the [VPC management interface](https://ap-southeast-1.console.aws.amazon.com/vpcconsole/).
   In the NAT gateway interface:
      + In the **Name** field, enter **My Natgw**.
      + In the **Subnet** field, select **Public subnet 2**.
      + In the **Connectivity type** field, select **Public**.
      + In the **Elastic IP allocation ID** field, click **Allocate Elastic IP** to create an Elastic IP.
      + Click **Create Nat Gateway**.
    ![natgw](/images/2.prerequisite/052-natgw.png)
2. Successfully created NAT gateway.
    ![natgw](/images/2.prerequisite/053-natgw.png)

3. In the Route table - Private interface:
      + Select **Routes**.
      + Select **Edit routes**.
   ![natgw](/images/2.prerequisite/054-natgw.png)
4. In the **Edit routes** interface:
      + Select **Add route**.
      + In the **Destination** field, enter **0.0.0.0/0**.
      + In the **Target** field, select **NAT Gateway**.
      + Click **Save changes**.
   ![natgw](/images/2.prerequisite/055-natgw.png)
5. Verify the routes.
   ![natgw](/images/2.prerequisite/056-natgw.png)