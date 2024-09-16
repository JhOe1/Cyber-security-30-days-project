# Day 7 - SOC Analyst Challenge

## Overview

Welcome to Day 7 of the 30-day SOC Analyst challenge.

### Objective
Today's session is focused on deploying and managing an Elastic Agent on a Windows Server for centralized monitoring and management using a Fleet server.

### Key Tasks
1. **Deploy a Fleet Server**:  
   Created a new Ubuntu server instance to act as the Fleet Server. The server was set up to manage and monitor our Windows server through a centralized platform.
   
2. **Configure Elastic Agent**:  
   Installed the Elastic Agent on the Windows Server created in Day 5 and ensured that it enrolled properly into the Fleet server for central monitoring.

3. **Firewall Configuration**:  
   Updated and troubleshooted firewall rules to allow proper communication between the Fleet Server and the Windows Server. Specifically, modified rules to allow connections on ports `9200` (ElasticSearch) and `8220` (Fleet server).

4. **Elastic Agent Troubleshooting**:  
   Faced some challenges during the enrollment process due to misconfigurations and firewall rules. Resolved the issues by updating firewall rules and adjusting the Fleet server settings in the Elastic GUI to ensure successful communication.

### Learnings
- **Firewall Management**:  
   Understanding how firewalls and port rules can affect the connection between servers in a monitoring setup.
   
- **Elastic Agent Enrollment**:  
   The importance of proper configuration, especially when dealing with self-signed certificates and ensuring that the necessary ports are open for agent communication.

- **System Logging**:  
   Successfully captured logs from the Windows Server, including Event Code `4625`, which represents a failed login attempt. This provided valuable insight into monitoring authentication attempts and other critical system events.

### Key Commands & Troubleshooting
- **Firewall Configuration**:
    ```bash
    ufw allow 9200  # Allow ElasticSearch port
    ufw allow 8220  # Allow Fleet Server port
    ```

- **Elastic Agent Installation**:
    ```bash
    sudo ./elastic-agent install --url=https://<FLEET_SERVER_IP>:8220 --fleet-server-es=https://<ELASTICSEARCH_IP>:9200
    ```

- **Certificate Error Resolution**:
    ```bash
    sudo ./elastic-agent install --url=https://<FLEET_SERVER_IP>:8220 --fleet-server-es=https://<ELASTICSEARCH_IP>:9200 --insecure
    ```

### Conclusion
By the end of this session, I successfully set up and enrolled a Windows Server into the Fleet management server. This marks an important step in building centralized monitoring capabilities for a security operations center (SOC). Future lessons will involve diving deeper into log analysis and leveraging system activity monitoring tools such as **Sysmon**.

---

## Next Steps
In the next session, I will explore **Sysmon**—a powerful tool that monitors and logs system activity on Windows machines, offering valuable insights for threat detection and system auditing.

Stay tuned!

---

**Follow the challenge:**  
- GitHub: [Your GitHub Profile]  
- Twitter: [Your Twitter Handle]

Thank you for following along on this journey!

