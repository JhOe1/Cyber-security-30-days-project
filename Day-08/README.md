# Day 5 - Enhancing Endpoint Visibility with Sysmon

### Objective:
Endpoint visibility is crucial for effective incident detection and response. While Windows systems have default logging enabled, these settings are insufficient for capturing critical events like process creations. Today, I explored how to significantly enhance this visibility using Sysmon, a powerful tool from Microsoft Sysinternals.

### What is Sysmon?
Sysmon (System Monitor) is a free tool that provides detailed information about process creations, network connections, file creations, and much more. By installing and configuring Sysmon on Windows endpoints, I can capture a variety of events essential for monitoring and investigating suspicious activity.

### Key Capabilities:
- **Process Creations (Event ID 1):** Sysmon logs new processes, including their command lines and file hashes, which helps identify malicious activity and use open-source intelligence (OSINT) tools to look up hashes.
- **Network Connections (Event ID 3):** When enabled in the configuration, this tracks source and destination IP addresses, ports, and the associated processes. This is critical for detecting unusual outbound connections, such as Command and Control (C2) traffic.
- **Correlating Events with Process GUID:** Sysmon records a unique Process GUID, allowing the correlation of different event types to build a full picture of an attack or compromise.

### Noteworthy Event IDs:
- **Process Creation (ID 1):** Logs any new processes with command line details and file hashes.
- **Network Connections (ID 3):** Logs network connections made by processes, including source/destination IPs and ports (must be enabled in the config).
- **Driver & Image Loads (IDs 6 & 7):** Detect potential defense evasion techniques like process injection. These can trigger false positives, but careful analysis using the process GUID helps reduce noise.
- **DNS Queries (ID 22):** Logs domain requests, which can be useful for identifying endpoints contacting malicious or suspicious domains.

### Conclusion:
Sysmon is a versatile and customizable tool that improves visibility into endpoint activity. By leveraging its event IDs and correlating data, it's possible to uncover hidden malicious behaviors. The ability to detect techniques such as process injection, suspicious network connections, and credential access attempts makes it invaluable for SOC analysts.



