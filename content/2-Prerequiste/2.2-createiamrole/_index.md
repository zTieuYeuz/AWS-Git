---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Create IAM Role

In this step, we will create an IAM Role. This IAM Role will be assigned the **AmazonSSMManagedInstanceCore** and **CloudwatchLogsFullAccess** policies, which allow the EC2 instance to communicate with the Session Manager and CloudWatch logs.

1. Access the [IAM service management interface](https://console.aws.amazon.com/iamv2/)
2. In the left navigation pane, select **Roles**. Click **Create role**.

![role1](/images/2.prerequisite/039-iamrole.png)

3. Click **AWS service** and then click **EC2**. 
  + Click **Next: Permissions**.  

![role1](/images/2.prerequisite/040-iamrole.png)

4. In the search bar, 
  + Input **AmazonSSMManagedInstanceCore** and press Enter to search for this policy.
  + Select the **AmazonSSMManagedInstanceCore** policy.
  + Then input **CloudwatchLogsFullAccess** and press Enter to search for this policy.
  + Select the **CloudwatchLogsFullAccess** policy.
  + Click **Next: Tags**.

![addpolicy](/images/2.prerequisite/041-iamrole.png)
![addpolicy](/images/2.prerequisite/042-iamrole.png)

5. Click **Next: Review**.
6. Name the Role **SSM-Role** in the Role Name field.  
  + Click **Create Role**.

![NameRole](/images/2.prerequisite/043-iamrole.png)

7. Next, we will assign this role to the public and private EC2 instances. Access the [EC2 management interface](https://ap-southeast-1.console.aws.amazon.com/ec2).
  + Click **Instances**.
  + Check **EC2_Private**.
  + Click **Action** -> Click **Security**.
  + Click **Change security groups**.

![Attachrole](/images/2.prerequisite/044-iamrole.png)

8. Select the **SSM-Role** you just created.
   + Click **Update IAM role**.

![Attachrole](/images/2.prerequisite/045-iamrole.png)