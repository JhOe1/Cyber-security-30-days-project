
### Day 17 - Creating a Dashboard for RDP Activity

On Day 17 of the 30-Day SOC Analyst Challenge, the objective was to create a dashboard that monitors RDP activity from the Windows server established on Day 5. This involves visualizing failed and successful authentication attempts using the Elastic stack.

#### Steps:

1. **RDP Failed Authentication Map**  
   The process begins by constructing a map similar to the SSH map created earlier, but focusing on RDP failed authentication attempts.  
   Using event code `4625` and agent name filters, we query failed login events. These are plotted on a map, where geographical sources of the failed attempts (based on IP addresses) are visualized.  
   - **Example**: A significant number of failed attempts were observed from Russia, with over 39,000 events.

2. **RDP Successful Authentication Map**  
   Next, a query for successful RDP logins is created using event code `4624` and focusing on logon types 10 and 7.  
   The map displays successful RDP logins, like one originating from Indonesia within the last 15 minutes.

3. **Data Tables**  
   To enhance visibility, tables were added to the dashboard to list usernames, source IPs, and countries of origin for both failed and successful authentication attempts.  
   This provides a quick, detailed view of user activity alongside the geographical visualizations.

4. **SSH and RDP Dashboards**  
   The final dashboard displays both SSH and RDP activities. Authentication data for each protocol is grouped by success or failure, providing a comprehensive view of login attempts.

By the end of Day 17, a robust dashboard was built, showcasing real-time RDP activity and SSH authentication for monitoring purposes in a SOC environment.
