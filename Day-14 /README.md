# Day 14 of the 30-Day SOC Analyst Challenge

Today, the focus is on configuring an alert for detecting **SSH Brute Force attacks** and visualizing the attack patterns using the data collected. This exercise is critical in understanding how to identify and respond to brute force attacks in real-time, a key skill for any SOC analyst.

---

## Objective: Detecting SSH Brute Force Attacks

Brute force attacks are a common attack vector, where attackers repeatedly attempt to gain access by guessing credentials. The goal is to set up an alert that identifies these attacks by analyzing SSH logs for failed login attempts and then visualizing the origin of these attacks for a comprehensive overview.

### Step 1: Querying SSH Logs in Elasticsearch

The first step involves accessing the **Elasticsearch** instance and querying the SSH logs. These logs are being generated from the **SSH linux server**. Upon filtering, approximately **3298 events** were found, containing the relevant SSH data.

![vpc51](https://github.com/user-attachments/assets/0269292f-6928-4fef-9f44-ce2851b65ede)




### Step 2: Narrowing Down Failed Authentication Attempts

To identify potential brute force attacks, the focus is on failed login attempts. By filtering for the keyword `failed` in the logs, **30 events** were identified. This was the initial dataset, but further refinement was necessary.

![vpc52](https://github.com/user-attachments/assets/b966e2ed-a704-43ae-a5f3-620a61b40696)




### Step 3: Refining the Query

A key field in the logs, `system.auth.ssh.event`, was identified. This field tracks events like **failed**, **invalid**, and **accepted** password attempts. Adding this field to the data table provided a more detailed breakdown, reducing the total number of events to **39**.


![vpc53](https://github.com/user-attachments/assets/3a3e9c4c-2879-4b2b-8f27-04edf77aceec)




---


## Step 4: Identifying Targeted Usernames and IP Addresses

To better understand the attack, the next step was to analyze the targeted usernames and their originating IP addresses:
- The `user.name` field revealed common targets, such as `root`, `admin`, and `splunk`.
- The `source.ip` field provided insights into the geographical locations of the attack origin, showing a distribution across **The Netherlands**, **Hong Kong**, and the **Bulgaria**.
- By joining this information with country codes, the geographic sources of the attacks became clearer.


![vpc54](https://github.com/user-attachments/assets/54160f07-6060-49c5-bd19-be6f5462732e)









### Step 5: Filtering for Failed Login Attempts

Focusing specifically on failed login attempts, the query was refined to display **53 failed attempts**, providing a clearer view of the data relevant to the brute force attacks.


![vpc55](https://github.com/user-attachments/assets/6b603e7a-88b2-4b51-980f-8af650e84790)





---

## Step 6: Configuring the SSH Brute Force Alert

With the data properly filtered, the next step was to create an alert to notify when brute force attacks occur. 

- A query was saved as **SSH Failed Activity**, representing the failed login attempts.
- A search threshold rule was then created, named `ssh-bruteforce-activity`. This rule triggers an alert when **5 failed attempts** occur within a **5-minute window**. Testing the alert with various time ranges ensured that it functioned correctly.


![vpc56](https://github.com/user-attachments/assets/3396b1f0-cfe3-4976-8e01-1d75cbaeaf63)






---

## Step 7: Visualizing Attack Origins with a Map

To gain a more visual understanding of the attack patterns, a map visualization was created:

- Using the **Maps feature** in Elasticsearch, the source IP addresses were plotted on a **Choropleth map** to highlight the geographical distribution of the attacks.
- The map was enhanced by joining the data with **ISO country codes** to visualize attacks by country.


![vpc57](https://github.com/user-attachments/assets/6fc6eb79-eea8-4efb-8072-055a31cd65ff)




### Final Output: SSH Network Map Dashboard

A dashboard named **SSH Network Map** was created to monitor the incoming brute force attempts in real-time. This dashboard will serve as a quick reference for tracking attack patterns going forward.


![vpc58](https://github.com/user-attachments/assets/b27d94ee-a9c9-4671-91ca-f96bdb1c7e85)




---

## Conclusion

On Day 14, an effective **SSH Brute Force alert** was configured and a visual representation of the attack patterns was set up. These are critical tools for monitoring and responding to brute force attacks in real-time. The next phase will focus on building response mechanisms when alerts are triggered.

