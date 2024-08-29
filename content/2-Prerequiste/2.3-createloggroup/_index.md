---
title: "Create CloudWatch Log Groups"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.3 </b> "
---

### Create CloudWatch LogGroup

In this step, we will create 2 **Cloud Watch Log Groups**. The purpose:
   + Store and categorize AWS VPN logs to easily check and know the VPN status.
   + Store and categorize command logs used when accessing EC2 via SSM.

2. Go to the [Cloud Watch service management interface](https://ap-southeast-1.console.aws.amazon.com/cloudwatch/)
3. Create **Log Groups** for SSM:
   + Select **Log Groups**
   + Select **Create log group**
   + Enter ```/aws/ssm/hosts``` as the log group name
   + Select **Create**
   ![Loggroup](/images/2.prerequisite/046-LogGroup.png)
   ![Loggroup](/images/2.prerequisite/047-LogGroup.png)

4. Similarly, create **Log Groups** for VPN:
   + Enter ```vpns2s/log``` as the **Name**
   ![Loggroup](/images/2.prerequisite/048-LogGroup.png)