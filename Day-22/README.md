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
