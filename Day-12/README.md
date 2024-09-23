
# Day 12: SSH Server Setup and Real-Time Authentication Log Analysis

## Overview
In today's challenge, I successfully set up an SSH server in the cloud and analyzed authentication logs in real-time. The objective of this exercise was to familiarize myself with configuring a cloud-based server, accessing it remotely via SSH, and monitoring log files for potential unauthorized access attempts.

## Steps Taken

1. **Server Deployment**: 
   - Deployed a Linux-based cloud server using Ubuntu 24.04.
   - Configured the server with minimal resources (1 CPU, 1 GB memory), sufficient for this task.
  
     
![vpc40](https://github.com/user-attachments/assets/550139ac-4566-408c-b65f-b3162992db92)


  

2. **SSH Access**:
   - Accessed the server remotely through SSH using PowerShell.
   - Updated the server repositories (`apt-get update` and `apt-get upgrade`) to ensure it was up to date.
  

![vpc41](https://github.com/user-attachments/assets/37339d44-68e7-45da-86c2-38b3b1f34af1)






3. **Authentication Log Review**:
   - Navigated to the `/var/log` directory, where authentication logs are stored.
   - Focused on the `auth.log` file to monitor real-time authentication events.
   - Observed a variety of authentication attempts, including failed login attempts, indicative of potential brute force attacks.
  

![vpc42](https://github.com/user-attachments/assets/f3a11fe7-02e9-4949-96f7-940f9919e851)





4. **Analyzing Failed Authentication Attempts**:
   - Used the `grep` command to filter for failed login attempts.
   - Narrowed the scope to examine only the failed attempts targeting the root user account.
   - Employed the `cut` command to extract the IP addresses associated with these failed attempts for further investigation.
  


![vpc43](https://github.com/user-attachments/assets/ba70b28b-1906-49d8-bacb-47c308f6c640)


![vpc44](https://github.com/user-attachments/assets/d196360c-6e45-414e-9193-08e2c9714a32)



## Key Takeaways
- **Brute Force Attack Detection**: Through log analysis, I detected failed login attempts from external IP addresses, which is a typical indicator of brute force attacks. This exercise reinforced the importance of robust SSH security configurations.
- **Command Line Proficiency**: Leveraging basic Linux commands like `grep` and `cut`, I was able to efficiently parse logs and extract relevant data, showcasing the power of command-line tools for incident detection and response.

## Next Steps
In the next session, I will install the Elastic Agent on this SSH server to forward logs to an Elasticsearch instance. This will enable me to query and analyze logs in a more scalable and centralized manner.


