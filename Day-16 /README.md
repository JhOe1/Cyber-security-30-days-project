# Day 16 - Analyzing Authentication Logs and Setting up Brute Force Alerts

Welcome to **Day 16** of my **30-day SOC Analyst Challenge** 

Today’s focus is on analyzing the authentication logs from the Windows Server created on **Day 5** and configuring a Brute Force alert specific to this server.

---

## Step 1: Reviewing Authentication Logs

I begin by accessing the **Elastic Web UI** to examine authentication logs. 

1. **Navigate to Discover**: 
   - Click the hamburger icon on the top left and select **Discover**.
   - Set the time frame to **Today**, which will display events within this range. For my setup, this generated **31,627 events**.
  
     
  ![vpc61](https://github.com/user-attachments/assets/910c65c4-08f7-41a2-a40f-b4de727c527c)



2. **Filter for Windows Server Events**: 
   - Since we are interested in **RDP authentication** activities, I filtered for my Windows server by clicking on `agent.name` and selecting my specific server: **Vulnerable-Windows-Server**. This narrowed down the results to **15,165 events**.
  

![vpc62](https://github.com/user-attachments/assets/2e2821e4-e522-4408-99cf-4a51d3955391)



3. **Filter for Failed Logins**: 
   - The next step was filtering for failed login attempts, which typically indicate Brute Force activities. After a quick search, I found that **Event ID 4625** represents failed authentication attempts. Using this, I applied a query to filter the logs and reduce the results to **5,874 events**.
  
![vpc63](https://github.com/user-attachments/assets/51961658-e0e2-4c07-be2e-1fb87b0544b9)





4. **Identifying Source IPs and Usernames**: 
   - I modified the table to display the fields: `source.ip` and `user.name`. By expanding the first event in the table, I confirmed that the logs were showing the correct user (`user.name = "user"`) and the correct **source IP** address (`192.xxx.xxx.147`). 
   - I saved this query as **"RDP Failed Activity"** for future use.


![vpc64](https://github.com/user-attachments/assets/a8a5b181-17a4-48de-95e0-41b3bdc721d9)



---

## Step 2: Verifying RDP Logon Activity

To ensure the logs represented **RDP** activity, I initiated a failed login attempt on the server using **RDP** from my host machine. After attempting to log in with the credentials `User1` (and failing), the logs captured this event.

![vpc65](https://github.com/user-attachments/assets/85dcdd0b-653a-4024-80d5-2ebd56862e2c)


- **Logon Type 3** was recorded, which typically represents a **network-based logon** (including SMB or RDP).

For **successful RDP logons**, **Event ID 4624** is used with **Logon Type 10** indicating remote interactive logons, specifically for **RDP**.

---

## Step 3: Creating Brute Force Alerts

With the logs verified, the next step was to create a Brute Force alert based on **Event ID 4625**.

1. **Create Search Threshold Rule**:
   - Navigate to **Alerts** and select **Create Search Threshold Rule**.
   - I used a condition where the count of `event.code = 4625` is above 5 in a 5-minute window. This will trigger an alert when 5 or more failed logon attempts occur within a short period.
   - I saved this alert as **RDP Brute Force Activity For Vulnerable-Windows-Server**.
  
![vpc66](https://github.com/user-attachments/assets/ad7f04dd-febf-40c5-846a-3537d973ead5)










