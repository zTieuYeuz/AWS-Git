---
title : "Create CloudWatch Log Groups"
date : "`r Sys.Date()`"
weight : 3 
chapter : false
pre : " <b> 2.3 </b> "
---

### Create CloudWatch Log Groups

In this step, we will create 2 **CloudWatch Log Groups**. The purpose is:
    + To store and categorize logs of AWS VPN, allowing us to easily check and know the status of the VPN.
    + To store and categorize logs of commands used when accessing EC2 via SSM.
 
1. Access the [CloudWatch management interface](https://ap-southeast-1.console.aws.amazon.com/cloudwatch/).
2. Create **Log Groups** for SSM:
   + Select **Log Groups**.
   + Select **Create log group**.
   + In the Log group name field, input **/aws/ssm/hosts**.
   + Click **Create**.
   ![Loggroup](/images/2.prerequisite/046-LogGroup.png)
   ![Loggroup](/images/2.prerequisite/047-LogGroup.png)

3. Similarly, create **Log Groups** for VPN:
   + In the **Name** field, input **vpns2s/log**.
   ![Loggroup](/images/2.prerequisite/048-LogGroup.png)