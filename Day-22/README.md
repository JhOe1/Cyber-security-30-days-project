### Summary of Activity: Event Analysis and Dashboard Creation

In this project, I performed an in-depth analysis of Windows event logs to identify suspicious activities and enhance incident detection capabilities.

#### Part 1: Event Log Querying

1. **Initial Setup**: 
   - Established a query to filter Windows events based on specific event codes and providers, focusing on `Microsoft-Windows-Sysmon` and `Microsoft Defender`.
   
2. **Event Exploration**:
   - Analyzed various event IDs, including:
     - **Event ID 1**: Monitored process creation through tools such as PowerShell, CMD, and rundll32.
     - **Event ID 3**: Examined network connections initiated by processes.
     - **Event ID 50001**: Identified instances of Windows Defender being disabled.

3. **Data Insights**:
   - Extracted critical fields such as `timestamp`, `user`, `process`, `source IP`, and `destination IP` to understand the context of each event.
   - Focused on instances where the connection was initiated by the server to capture potential threats.

#### Part 2: Dashboard Development

1. **Dashboard Creation**:
   - Developed a new dashboard within the monitoring tool, organizing visualizations for:
     - Process creation activities (Event ID 1)
     - Network connections initiated by processes (Event ID 3)
     - Instances of Microsoft Defender being disabled (Event ID 50001)

2. **Visualization Enhancements**:
   - Customized visualizations to present data in a clear and concise format, utilizing tables to display essential fields while excluding irrelevant information.
   - Ensured that each panel within the dashboard provided actionable insights for security monitoring.

3. **Finalization**:
   - Saved the dashboard with relevant titles and descriptions to facilitate future reference and analysis.

Through this activity, I gained valuable experience in leveraging event log data for security monitoring and enhancing my skills in creating informative dashboards.





























Summary of the Dashboard Creation Process
In this project, I walked through the process of creating and refining alerts and dashboards to monitor suspicious activity using event codes and providers within the Windows environment.

Part 1
I initiated the process by analyzing event codes, particularly focusing on Event ID 1, which pertains to process creation through PowerShell, CMD, and RunDLL. After confirming the functionality of my queries, I updated the alert configurations to ensure they were capturing the necessary data accurately. With Event ID 3, which tracks network connections, I adjusted the queries to extract significant fields such as image names, source IP addresses, and destination ports.

Part 2
Continuing the work, I delved deeper into creating a comprehensive dashboard. For Event ID 50001, related to Microsoft Defender's status, I integrated relevant fields into the visualization. I formatted tables for clarity and streamlined the information displayed, focusing on key aspects of the events. I also implemented exclusions to filter out unnecessary data, ensuring that the dashboard provided meaningful insights into potential security threats.

Ultimately, I developed three distinct panels:

Process Created – Monitoring for the execution of PowerShell, CMD, and RunDLL.
Process Initiated Network Connections – Observing the network activities initiated by various processes.
Microsoft Defender Disabled – Tracking instances where Defender was turned off.
This exercise not only enhanced my skills in configuring alerts and dashboards but also solidified my understanding of the importance of visualizing security data to quickly identify and respond to threats.

I encourage anyone following this project to adapt and expand upon these dashboards to suit their specific security monitoring needs.
