# Day 13: Installing Elastic Agent on SSH Server for Log Ingestion

## Overview
Today, I focused on integrating my cloud-based SSH server from Day 12 with my Elasticsearch instance. The goal was to install an Elastic Agent on the server to enable centralized log ingestion and querying through Elasticsearch. This setup enhances visibility into authentication logs, allowing for detailed analysis of potential threats, such as failed login attempts.

## Steps Taken

1. **Navigating Elasticsearch Fleet Management**:
   - Accessed the Elasticsearch web UI.
   - Navigated to the Fleet management section by selecting it from the menu.
   - Created a new agent policy for my Linux SSH server, named `Linux-policy`, which defines how logs will be ingested from the server.
  
![vpc45](https://github.com/user-attachments/assets/b683e024-c1ff-4dea-8602-449ade98dbe9)




2. **Defining Log Paths**:
   - The agent policy was configured to monitor authentication logs located at `/var/log/auth.log` (for Ubuntu systems).
   - Confirmed that the log path was correctly set based on my server’s operating system, ensuring compatibility with Ubuntu/Debian systems (where `/var/log/secure` is used in Red Hat/CentOS distributions).
  

![vpc46](https://github.com/user-attachments/assets/5bc5f3d6-b00a-4808-bb4b-9130c3a52997)




3. **Agent Installation**:
   - Enrolled the SSH server in Fleet using the newly created agent policy.
   - Logged into the server via PowerShell, navigated to the appropriate directory, and executed the provided enrollment command.
   - Resolved an `x509 certificate signed by unknown authority` error by adding the `--insecure` flag, which is required when using a self-signed certificate.
   - Successfully installed the Elastic Agent, confirmed through both the CLI output and the Elasticsearch dashboard, where the agent’s enrollment status was verified.

![vpc47](https://github.com/user-attachments/assets/bf37a564-30f7-4fb3-bea1-d665e290cc97)


![vpc48](https://github.com/user-attachments/assets/171d4315-b5fe-45ac-ab4d-13645634ae61)


4. **Log Querying**:
   - Accessed the `Discover` section in Elasticsearch to view ingested logs.
   - Filtered the results by the agent name corresponding to my SSH server and located authentication events.
   - Analyzed failed authentication attempts, identifying a specific IP address (`178.128.161.183`) responsible for multiple failed login attempts targeting the root account.
  
![vpc50](https://github.com/user-attachments/assets/1736b9a1-1b8c-4165-a39e-231121625d02)




5. **Adding Authentication Failure Data**:
   - Queried Elasticsearch for `authentication failure` events related to the identified IP address.
   - Found 49 failed authentication events, each logged with detailed information about the source IP, time, and log message.
   - Added the `message` field to the table view for easier readability, allowing for quicker identification of relevant authentication failures.
  

![vpc49](https://github.com/user-attachments/assets/6eaa88a0-9635-4a99-bdce-85db6d24ff91)



## Key Takeaways
- **Streamlined Log Ingestion**: Setting up the Elastic Agent enabled seamless ingestion of SSH logs into Elasticsearch, improving centralized monitoring and analysis.
- **Efficient Log Analysis**: Utilizing Elasticsearch’s query capabilities, I was able to quickly identify suspicious activity, such as brute force login attempts, demonstrating the value of real-time log monitoring.
- **Error Resolution**: Encountering and resolving the `x509 certificate` issue served as a reminder of the importance of understanding SSL/TLS in secure communications.




