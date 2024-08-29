---
title: "Configure Dynamic Route BGP"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

1. In the Fortigate configuration interface, configure routing for both tunnels according to the file:
   + Select **Network** -> Select **BGP**
   + Input **Router-ID** as **118.107.96.13**
   + Select **Apply**
      ![bgp](/images/4.vpnsitetositefortigate/BGP-1.png)
   + Select **Neighbor** -> **Create new**. The **Add Neighbor** dialog appears to configure tunnel 1
   + Input **IP** as **169.254.52.5**, **Remote AS** as **64512**
      ![bgp](/images/4.vpnsitetositefortigate/BGP-2.png)
   + Input **IP/Netmask** as **172.16.4.0/24**. This is the address range that **Fortigate** will use to advertise to AWS
      ![bgp](/images/4.vpnsitetositefortigate/BGP-3.png)
{{% notice info %}}

Note that this configuration is slightly different from the file. If you need to advertise any network layer to AWS, fill in each network layer.

{{% /notice %}}
2. Configure neighbors for tunnel 2
   + Select **Neighbors** -> **Create New**. The **Add Neighbor** dialog appears to configure tunnel 2
      ![bgp](/images/4.vpnsitetositefortigate/BGP-4.png)
   + Input **IP** as **169.254.52.5**, **Remote AS** as **64512** -> Select **OK**
   + Select **Apply**
      ![bgp](/images/4.vpnsitetositefortigate/BGP-5.png)