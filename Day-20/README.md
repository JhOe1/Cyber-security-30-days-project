## Day 20: Setting Up a Mythic C2 Instance

On Day 20, I explored setting up my own Mythic Command and Control (C2) instance to further understand how C2 frameworks operate within a cybersecurity context.

### Key Activities:
1. **Cloud Deployment**:
   - I used Vultr cloud services to deploy a new server, running on Ubuntu, to host my Mythic C2 instance.
   - This involved setting up a virtual machine with specific configurations for memory and CPU allocation.

2. **Kali Linux Installation**:
   - Alongside the server, I installed Kali Linux on my local machine using VMware, ensuring it was properly configured for the tasks ahead.

3. **Mythic Installation**:
   - After setting up the cloud environment, I installed Docker and the necessary prerequisites to run Mythic.
   - I cloned the Mythic GitHub repository and executed the required scripts to initiate the installation process.

4. **Firewall Configuration**:
   - For added security, I configured a firewall to limit access to only my computer and other target machines. This step was essential to prevent unauthorized access to my Mythic server.

5. **Mythic Login**:
   - I logged into the Mythic web interface using the default credentials, accessed the environment file for configurations, and explored the Mythic C2 dashboard.

6. **Mythic Dashboard Overview**:
   - The dashboard provides a high-level view of payloads, callbacks, and key services related to C2 operations. I explored options like generating new payloads, fetching task mappings, and reviewing MITRE ATT&CK mapping features.

### Conclusion:
Day 20 focused on setting up a Mythic C2 instance within a secure cloud environment, providing a hands-on experience with the installation and initial configuration of a C2 framework. This setup lays the foundation for generating payloads and conducting controlled C2 operations in the following days, reinforcing key concepts in adversary simulation and defense strategies.


