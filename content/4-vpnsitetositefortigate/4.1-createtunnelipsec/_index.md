---
title: "Create IPSEC Tunnel"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

In this exercise, we will create and configure IPSEC on the **Fortigate** device based on the [Configuration file](#download-configuration) downloaded from Amazon.

{{% notice info %}}

1 Important note is that this [Configuration file](#download-configuration) contains all the configuration parameters for all exercises from 4.1 -> 4.5.
{{% /notice %}}

1. Access VPC
    - Select **Site-to-Site VPN Connection**
    - Select the created VPN Connection
    - Select **Download Configuration**
    ![vpnfg](/images/4.vpnsitetositefortigate/001-vpnfg.png)

2. In the **Download Configuration** dialog, choose the appropriate appliance: In this exercise, we will use **Fortigate**.
    - **Vendor**: Select **Fortinet**
    - **Platform**: Select **Fortigate 40+series**
    - **Software**: Select **FortiOS 6.4.4+ (GUI)**
    - **IKE version**: Select **ikev1**
    - Select **Download**.
    ![vpnfg](/images/4.vpnsitetositefortigate/002-vpnfg.png)
{{% notice info %}}

Note that in this step, we choose ikev1 to help you understand the basic configuration for easier troubleshooting. For actual deployment, you should use **ikev2**. The biggest advantage of ikev2 is that the handshake negotiation process between the two sites will be faster and support more security algorithms.

{{% /notice %}}

##### download-configuration
3. Save the configuration file information to a folder:
    - Then, based on the provided configuration, configure these settings for your device.
    ![vpnfg](/images/4.vpnsitetositefortigate/003-vpnfg.png)

4. In the Fortigate interface, create VPN tunnel 1:
    - Select **VPN** -> IPsec Wizard
    - **Template type** select **Custom**
    - Enter **Name** as **VPN AWS Tunnel 1**
    - Select **Next**
    ![vpnfg](/images/4.vpnsitetositefortigate/004-vpnfg.png)

5. In the **New VPN Tunnel** interface, create tunnel 1 for the VPN:
    #### Phase 1
    - Enter **IP address** as **18.143.226.251**
    - Select **Interface** as **Wan Internet(Wan 1)**
    - Select **NAT Traversal** as **Disable**
    - Enter **Pre-shared Key** as provided in the file **DS6CXQf8YMvA0E4wRo4uDGRtcVofGiad**
    - In **Phase 1 Proposal**, delete all previous lines and configure **Encryption** as **AES128**, **Authentication** as **SHA1**
    - Uncheck **14,5** in **Diffie-Hellman Groups**. Only select **2**
    - Enter **Key Lifetime (seconds)** as **28800**
    ![vpnfg](/images/4.vpnsitetositefortigate/005-vpnfg.png)
    #### Phase 2
    - Click **+** in **Phase 2 Selectors**
    - In **Phase 2 Proposal**, delete all previous lines and configure **Encryption** as **AES128**, **Authentication** as **SHA1**
    - Uncheck **14,5** in **Diffie-Hellman Groups**. Only select **2**
    - Select Auto-negotiate
    - Enter **Seconds** as **3600**
    - Click **OK** to create
    ![vpnfg](/images/4.vpnsitetositefortigate/006-vpnfg.png)
    ![vpnfg](/images/4.vpnsitetositefortigate/007-vpnfg.png)

6. In the **New VPN Tunnel** interface, do the same for **tunnel 2** as for **tunnel 1**:
    - Reopen the previously downloaded **config file**, find and open the parameters for tunnel 2
        ![vpnfg](/images/4.vpnsitetositefortigate/008-vpnfg.png)
    - Configure **Phase1** and **Phase2** similarly to **Tunnel 1**
    ![vpnfg](/images/4.vpnsitetositefortigate/009-vpnfg.png)
    ![vpnfg](/images/4.vpnsitetositefortigate/010-vpnfg.png)
    ![vpnfg](/images/4.vpnsitetositefortigate/011-vpnfg.png)

7. Verify the interface to ensure we have a total of **2 tunnels** configured
    ![vpnfg](/images/4.vpnsitetositefortigate/012-vpnfg.png)