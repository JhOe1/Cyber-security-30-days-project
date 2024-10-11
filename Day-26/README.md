# Day 26: Investigating SSH Brute Force Alerts

**Welcome to Day 26 of the 30-day "My D for SOC Analyst" challenge!**  
This challenge aims to equip aspiring SOC analysts with practical experience in 30 days.

---

## Objective

In this session, you will learn how to investigate SSH Brute Force alerts effectively.

---

## Steps for Investigation

### 1. Access Alerts
- Click the **hamburger icon** in the top-left corner.
- Select **Alerts** under the Security tab.

### 2. Review Alerts
- Choose an alert from **August 14th**.
- Expand the alert details to analyze:
  - Description: Detects failed authentications towards the `root` account.
  - Source IP: `194.50.201.6`
  - Events: **7 events within 5 minutes**

### 3. Utilize Timelines
- Click on **Timelines** to create a new timeline or use templates to explore user-related alerts.

---

## Investigative Methodology

When investigating SSH Brute Force alerts, consider:

1. **Source IP Analysis**: 
   - Is the IP known for Brute Force attacks?

2. **Affected Users**: 
   - Were there any successful logins?

3. **Post-Login Activity**: 
   - What actions occurred post-login?

---

## Detailed Investigation

### Step 1: Source IP Check
- **IP Address**: `194.50.201.6`
- **AbuseIPDB**: Reported **1,816 times** (Confidence: **100%**).
- **GreyNoise**: Confirmed as a malicious **ZMap client SSH brute forcer**.

### Step 2: Affected Users Review
- Use **Kibana**:
  - Go to **Discover** and search for the IP.
  - Filter results by `user.name`: **4 distinct users** affected:
    - `root`
    - `Oracle`
    - `guest`
    - `test`

### Step 3: Successful Logins Check
- Search for **"accepted"** in the logs: **0 results**.
- Check with **"Accept"**: **0 results**.
- Conclusion: No successful logins recorded.

---

## Final Notes

Document your findings in your ticketing system. Modify detection rules to send alerts directly to your ticketing system:

1. **Navigate to Rules** > **Detection Rules**.
2. Edit the SSH Brute Force rule:
   - Set up **Webhook** actions for alert creation.
   - Customize alert messages for clarity.

---

This concludes Day 26. Continue practicing to enhance your SOC analysis skills!

