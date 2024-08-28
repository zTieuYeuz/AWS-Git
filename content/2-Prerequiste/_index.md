---
title : "Preparation Steps"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}

Before starting to configure VPN with AWS and Fortinet, you should prepare some knowledge about static and dynamic routing protocols. You can refer to a brief introduction about Dynamic Routing **BGP** which will be used in this lab in section 4.

{{% /notice %}}

{{% notice info %}}

To perform this lab, you need to further study Fortigate firewall. You can virtualize this firewall on VMware with a 14-day license for the lab. Here, I am using Fortigate 100F hardware (Version v6.4.12 build2060 (GA)).

{{% /notice %}}

{{% notice info %}}

You need to create 2 Linux instances in the public subnet and private subnet to perform this practice.

{{% /notice %}}

To learn how to create EC2 instances and VPC with public/private subnets, you can refer to the following labs:
  - [Introduction to Amazon EC2](https://000004.awsstudygroup.com/vi/)
  - [Working with Amazon VPC](https://000003.awsstudygroup.com/vi/)

To learn how to create IAM roles with ssm and cloudwatch permissions, you can refer to the following labs:
  - [AWS CloudWatch Workshop](https://000008.awsstudygroup.com/)
  - [Working with Amazon System Manager - Session Manager](https://000058.awsstudygroup.com/vi/)

To learn about routing protocols, you can refer to:
  - [Border Gateway Protocol (BGP)](https://aws.amazon.com/what-is/border-gateway-protocol/)

Appendix
1. [Prepare VPC and EC2 Instance](2.1-createvpc_ec2/)
2. [Create IAM Role](2.2-createiamrole/)
3. [Create CloudWatch Log Group](2.3-createloggroup/)
4. [Enable ssm feature to store logs in CloudWatch](2.4-enablelogssm/)
5. [Prepare Fortigate device](2.5-fortigate/)