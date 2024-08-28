---
title : "Manage SSM Session Logs with CloudWatch Logs"
date : "`r Sys.Date()`"
weight : 4 
chapter : false
pre : " <b> 2.4 </b> "
---

In this step, we will enable the **CloudWatch** feature in **SSM** to allow access logs and command execution logs when users access EC2 to be pushed to **CloudWatch**.

1. In the [AWS Systems Manager](https://ap-southeast-1.console.aws.amazon.com/systems-manager) interface:
   + Select **Session Manager**.
   + Select the **Preferences** tab.
   + Select **Edit**.
   
   ![enablessm](/images/2.prerequisite/049-SSM.png)
   
   + In the CloudWatch logging section:
   + Select **Enable**.
   + Uncheck **Enforce encryption**.
   + Select **vpns2s/log**.
   + Select **Save**.
   ![enablessm](/images/2.prerequisite/050-SSM.png)
   ![enablessm](/images/2.prerequisite/051-SSM.png)