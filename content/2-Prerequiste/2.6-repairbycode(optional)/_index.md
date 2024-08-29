---
title: "Prepare Environment with Code (Optional)"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 2.6 </b> "
---

In this section, we will guide you on how to deploy the environment as in sections 2.1 and 2.2 using **Infrastructure as Code**. Since the process is repeated many times, creating and configuring the lab in sections 2.1 and 2.2 takes a lot of time. Therefore, this section will guide you through some basic commands to deploy the environment as in sections 2.1 and 2.2 using Terraform.

{{% notice info %}}

This code will create the entire environment as in sections 2.1 and 2.2 [Code here](https://github.com/thangtranit90/InfraAsCode_AWS.git)

{{% /notice %}}

To use and write Terraform, you need to learn how to install and write code with Terraform:
  - [Install Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
  - [Module deployment syntax](https://developer.hashicorp.com/terraform/language/modules/syntax)
  - [Use available built-in modules](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)
  - [Install Terraform plugin for VS Code](https://github.com/hashicorp/vscode-terraform)

To deploy using Terraform on Amazon, you need to install and configure the AWS CLI with **access key** and **secret key** credentials. Refer to:
  - [Install and get familiar with AWS CLI on Windows](https://000011.awsstudygroup.com/vi/)

Usage Instructions:
1. Open the INFRAASCODE_AWS source folder in **VS Code**
   + Navigate to the **Singapore** directory
   + Find the **terraform.tfvars** file to declare the necessary information to initialize all resources in labs 2.1 and 2.2
     + **region** = "ap-southeast-1"
     + **availability_zone_1** = "ap-southeast-1a"
     + **availability_zone_2** = "ap-southeast-1b"
     + **cidr_block** = "10.10.0.0/16"
     + **public_subnet_ips** = ["10.10.1.0/24", "10.10.2.0/24"]
     + **private_subnet_ips** = ["10.10.100.0/24", "10.10.200.0/24"]
     + **instance_type** = "t2.micro"
     + **role_name** = "SSM-Role"
   ![tf](/images/2.prerequisite/064-terraform.png)
2. Open PowerShell in **VS Code**. Navigate to the Singapore directory
   + Enter ```terraform init``` to download the necessary modules and plugins for AWS.
   ![tf](/images/2.prerequisite/065-terraform.png)
   + After downloading, enter ```terraform plan``` to check the information of the resources to be created.
   + A total of **26 resources** will be deployed to AWS
   ![tf](/images/2.prerequisite/066-terraform.png)
   + After careful checking, enter ```terraform apply``` to start deploying resources to AWS
   + Check the information one more time. At **Enter a value**, enter **yes** to deploy. Enter **no** if you do not want to deploy
   ![tf](/images/2.prerequisite/067-terraform.png)
   + The deployment process takes a few minutes
   ![tf](/images/2.prerequisite/068-terraform.png)
   ![tf](/images/2.prerequisite/069-terraform.png)