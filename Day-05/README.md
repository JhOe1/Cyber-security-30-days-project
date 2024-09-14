# Day 5: Setting Up a Target Machine in the Cloud

Today, I focused on setting up a **Windows Server** in the cloud, acting as the target machine with **Remote Desktop Protocol (RDP)** exposed to the internet. This marks an important step in monitoring and understanding potential attack vectors as part becoming a  SOC Analyst.

## Step-by-Step Setup:

1. **Platform Selection**: I deployed the server on **Vultr**, selecting a cloud compute instance with a shared CPU. Since performance demands are minimal for this experiment, I opted for the most cost-effective option of **$24 per month**, featuring:
   - **1 vCPU**
   - **2 GB Memory**

![vpc21](https://github.com/user-attachments/assets/8f358b6e-2fdb-4cf4-93b9-743cd6eb30d6)





2. **Networking Setup**:
   - I initially considered adding this server to the **Virtual Private Cloud (VPC)** where my OS Ticket and Fleet Servers are hosted. However, for enhanced security and isolation, I decided against it to minimize exposure in the event of a compromise. Instead, I kept this Windows Server separate from the VPC.
   - No **IPv6** and **auto backups** were selected as these were not necessary for this exercise.

3. **Firewall**: Left the **firewall group** unconfigured to ensure open access to the server from the internet, simulating a real-world scenario where a server might be improperly exposed.

4. **Server Naming**: Following the naming convention for the challenge, I named the server:
   - **mydefer-win-[username]**. For this example, I used "**mydefer-win-stevenrocks**."

## Validation and Remote Access:

After deployment, I confirmed the server was running and accessible via **RDP**:
- Copied the public IP address and connected using **Remote Desktop**.
- Successfully logged in and confirmed the server was live.

## What’s Next:

With **RDP exposed to the internet**, I’ll soon begin seeing login attempts and other potential attack traffic on this machine. This data will later help me analyze common attack patterns, brute-force attempts, and suspicious behavior sourced from the internet. In the next phase, I will set up a **Fleet Server** for centralized endpoint management.

---

## Insights and Learning:

By isolating the Windows Server from the rest of the network, I’ve added a critical layer of security, ensuring that if compromised, it won’t affect the other components of my infrastructure. Monitoring this server for real-world attacks will provide hands-on experience with log analysis and incident response, skills essential for any SOC analyst.


