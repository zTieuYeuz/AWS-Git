---
title : "Configuring Site-to-Site VPN on Fortigate"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

Before configuring, let's briefly understand the dynamic routing protocol **BGP** and why it should be used.

**Border Gateway Protocol (BGP)** is a **dynamic** routing protocol used on the Internet to exchange information between different networks. It is one of the most important protocols that help network systems exchange information and determine the optimal path for data transmission. BGP is designed to operate in large network systems, especially in the global Internet network, where hundreds of thousands of networks need to be interconnected.
**BGP** can determine the data transmission path based on multiple attributes such as bandwidth, quality, and the number of network hops the data needs to traverse. This helps the protocol choose the most optimal path to transmit data from source to destination efficiently and quickly.

Additionally, BGP plays a role in keeping the Internet operating stably by periodically updating routing information, reliably and flexibly.
BGP is a good choice for large, complex networks that require automation and flexibility if there are many networks. Compared to static routes, BGP has superior advantages:

| **Attribute**                 | **BGP (Border Gateway Protocol)**          | **Static Route**                        |
|:----------------------------:|:------------------------------------------:|:--------------------------------------:|
| **Automation and Flexibility**| Automatically learns and adjusts routes when there are changes in the network. | Requires manual configuration of all routes, manual updates needed when changes occur. |
| **Scalability**               | Suitable for large networks, handles millions of routes. | Suitable for small or simple networks, difficult to manage as the network expands. |
| **Routing Policies**          | Supports complex routing policies based on multiple attributes. | Does not support complex routing policies. |
| **Resilience**                | Automatically switches routes in case of failure, ensuring quick recovery. | Manual configuration of backup routes required, not flexible. |
| **Security**                  | Supports security mechanisms like MD5, but requires complex management. | Simpler, less prone to attacks but can still be misconfigured. |
| **Use Cases**                 | Suitable for large, complex networks with multiple ISPs, requiring automation and quick recovery. | Suitable for small, simple networks, not requiring automation or complex recovery. |


### Contents
  - [Create IP Sec Tunnel](4.1-createvpc/)
  - [Configure Tunnel 1 and Tunnel 2 Interfaces](4.2-configinterfacetunnel/)
  - [Configure BGP Routing](4.3-configroutingbgp/)
  - [Create Policies for VPN](4.4-createpolicy/)
  - [Check VPN Status](4.5-checkstatusvpn/)