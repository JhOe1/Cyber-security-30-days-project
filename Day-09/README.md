# Day 9 - SOC Analyst Challenge

**Objective:**  
Today's challenge focuses on installing and configuring Sysmon on the Windows Server machine created during Day 5. Sysmon plays a crucial role in monitoring and detecting malicious activities by logging various system events.

---

## Steps:

1. **Sysmon Installation:**
   - Downloaded the latest version of Sysmon (v15.15).
   - Connected to the Windows Server machine via Remote Desktop.
   - Navigated to Sysmon’s official page on Microsoft Learn to download the binaries.
   - Extracted the Sysmon binaries and prepared them for configuration.

2. **Sysmon Configuration:**
   - Obtained a widely-used Sysmon configuration file from Olaf's GitHub repository.
   - Downloaded the `sysmon-config.xml` file and saved it in the Sysmon directory.
   - Opened PowerShell as an administrator and navigated to the Sysmon directory.
   - Installed Sysmon using the following command:
     ```bash
     sysmon64.exe -accepteula -i sysmon-config.xml
     ```
   - Verified successful installation by checking the Sysmon service and confirming the generation of logs in Event Viewer.

3. **Verifying Logs:**
   - Opened Event Viewer and navigated to `Applications and Services Logs > Microsoft > Windows > Sysmon`.
   - Confirmed that Sysmon was logging events, including event ID 3 (network connections).

---

## Key Takeaways:

- Sysmon is now actively monitoring system events on the Windows Server.
- Understanding Sysmon's event logs, such as network connections (Event ID 3), helps in analyzing potential security incidents.
- This configuration lays the groundwork for integrating logs into Elasticsearch, which will be covered in upcoming days.

---

## Next Steps:
- In the next session, I'll integrate Sysmon and Microsoft Defender logs into the Elasticsearch instance. This will further enhance our ability to analyze and visualize the data for incident response.

---

Stay focused, and let's keep building toward a robust security monitoring setup.
