# Day 10: Ingesting Sysmon and Microsoft Defender Logs into Elasticsearch


## Objective
The primary goal for today is to ingest event logs from Sysmon and Microsoft Defender into Elasticsearch for further analysis. By the end of this day, I’ll have configured Elasticsearch to collect and display both Sysmon and Defender logs, providing deeper visibility into the system’s activities.

### Steps Covered

1. **Log in to Elasticsearch**
   - Started by logging into my Elasticsearch instance and navigated to the `Add Integrations` section to configure log collection.

2. **Add Custom Windows Event Logs**
   - Set up log ingestion for Sysmon by selecting the **Custom Windows Event Log** package. This package allows the ingestion of events from various Windows Event log channels.
   - Configured the integration to target the Sysmon event log, ensuring it collected the appropriate operational logs.

3. **Set Up Sysmon Integration**
   - Retrieved the Sysmon channel name directly from the Windows Server Event Viewer and input it into the Elasticsearch configuration.
   - Applied this configuration to the existing Windows policy created earlier, ensuring all event logs from Sysmon are properly captured.

4. **Add Microsoft Defender Integration**
   - Followed the same process for Microsoft Defender, focusing on critical event IDs (1116, 1117, and 50001) to ensure that only relevant security logs were ingested, such as malware detection events and real-time protection statuses.

5. **Testing the Configuration**
   - Conducted tests by disabling Windows Defender on the server to trigger event ID 50001. After re-enabling the protection, confirmed the logs were ingested successfully into Elasticsearch.

6. **Troubleshooting**
   - Resolved connection issues by adjusting firewall settings to allow incoming connections to Elasticsearch on port 9200. This step ensured that agents could communicate with the server, enabling smooth log ingestion.

### Key Takeaways

- **Event IDs Matter**: Only ingesting relevant event IDs (like 1116, 1117, and 50001) minimizes noise in the SIEM and helps focus on actionable data.
- **Firewall Configurations Are Crucial**: Allowing proper firewall rules, such as permitting traffic on port 9200, is essential for establishing and maintaining agent connectivity with Elasticsearch.
- **Sysmon and Defender Logs**: Collecting logs from both Sysmon and Defender offers comprehensive insight into system events, from basic operational logs to detailed security alerts.

