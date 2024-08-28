---
title : "Creating a Virtual Private Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---




### Creating a Virtual Private Gateway

1. **Access the VPC Console**
    + Select **Virtual Private Gateway**
    + Click **Create Virtual Private Gateway**
    ![vpg](/images/3.connect/Virtual%20private%20GW.png)

2. **In the Create Virtual Private Gateway Interface**
    + For the Name tag, enter **VPN TO DC**
    + Select Amazon default ASN
    + Click **Create virtual private gateway**
    ![vpg](/images/3.connect/Virtual%20private%20GW2.png)

3. **Attach the Virtual Private Gateway to a VPC**
    + Click **Actions**
    + Select **Attach to VPC**
    ![vpg](/images/3.connect/Virtual%20private%20GW3.png)

4. **In the Attach to VPC Interface**
    + Choose **VPC ASG**
    + Click **Attach to VPC**
    ![vpg](/images/3.connect/Virtual%20private%20GW4.png)

5. **Complete the Process and Check that the State is Attached**
    ![vpg](/images/3.connect/Virtual%20private%20GW5.png)
