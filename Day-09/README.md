# Day 9 - Setting up Sysmon the Windows Server

## Objective:
In today’s session, I successfully installed and configured Sysmon on the Windows Server machine created on Day 5. The goal was to enable detailed monitoring of system events through Sysmon logging, which will be essential for detecting and analyzing potential security incidents.

---

## Process:

1. **Sysmon Installation**:
   - I began by downloading the latest version of Sysmon (v15.15) from the official [Microsoft Learn](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) page.
   - After connecting to my Windows Server via RDP, I navigated to the Sysmon page, downloaded the binaries, and extracted them in the appropriate directory.
![vpc30](https://github.com/user-attachments/assets/03ea87a1-593d-4908-b6d9-f8ed4c138668)





2. **Obtaining the Configuration File**:
   - A well-known Sysmon configuration file created by Olaf was selected for this task. I located it on [GitHub](https://github.com/olafhartong/sysmon-modular) and saved the `sysmon-config.xml` file in the Sysmon directory.
   - The configuration file ensures that Sysmon logs key system events, such as network connections and process creations, which are crucial for security monitoring.
  

![vpc31](https://github.com/user-attachments/assets/c886b88f-b818-4715-9d83-348eeb952df6)




3. **Sysmon Configuration and Service Setup**:
   - Using PowerShell (run as Administrator), I navigated to the Sysmon directory and installed Sysmon with the following command:
     ```bash
     sysmon64.exe -i sysmonconfig.xml
     ```
   - After agreeing to the license, Sysmon was installed, and I verified the Sysmon service was running successfully by checking Windows Services.

4. **Verifying Event Logs**:
   - After installation, I opened **Event Viewer** and navigated to `Applications and Services Logs > Microsoft > Windows > Sysmon > Operational`.
   - Event ID 3, which logs network connections, was successfully generated and displayed in the logs.
   - This confirmed that Sysmon was not only installed correctly but also actively monitoring system activity and generating useful data.

![vpc32](https://github.com/user-attachments/assets/cc4dfabd-6b27-4083-9120-0eed98b60d5a)


---

## Key Takeaways:

- **Sysmon's Role**: By monitoring critical system events such as network connections (Event ID 3), Sysmon provides valuable insight into potential security incidents, helping with threat detection and investigation.
- **Configuring Sysmon**: Proper configuration is key to getting the most out of Sysmon. Using an established configuration file like Olaf's allows for comprehensive monitoring.
ontinue building a complete security monitoring environment!

---
