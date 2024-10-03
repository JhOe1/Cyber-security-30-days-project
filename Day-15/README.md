### **Day 15: Understanding and Mitigating RDP Abuse**

#### **Overview:**
Today marks another step in my 30-day SOC Analyst challenge, where I dive into one of the most exploited protocols in modern cyber-attacks—**Remote Desktop Protocol (RDP)**. With over **90% of ransomware attacks in 2023** reportedly involving RDP misuse (Sophos), understanding how attackers exploit this protocol is critical. My goal for this challenge is to deepen my knowledge of RDP exploitation and enhance my ability to defend against it.

---

#### **What is RDP?**
RDP, or **Remote Desktop Protocol**, is a Microsoft-developed protocol that allows users to remotely access and control another computer over **TCP port 3389**. While RDP is widely used in IT environments for administrative purposes, its exposure to the internet often creates a significant attack vector. In practice, attackers leverage weak or exposed RDP instances to gain unauthorized access to systems, a fact that has contributed to its frequent appearance in cyber incidents.

---

#### **How Attackers Exploit RDP:**
Attackers typically abuse RDP through two main methods:

- **Brute force attacks** on exposed RDP services, attempting to guess passwords.
- Exploiting **stolen credentials** obtained from phishing attacks or other breaches.

Once they have access, attackers frequently engage in **credential dumping** to expand their privileges and move **laterally** within a network. RDP attacks often serve as an entry point for more serious compromises, such as ransomware deployment or data exfiltration.

---

#### **How I Identified Exposed RDP Services:**
To proactively identify vulnerable RDP instances, I used two powerful tools: **Shodan** and **Censys**. These platforms provide a clear view of RDP services exposed to the public internet, giving SOC analysts like myself a chance to preemptively close any gaps in our security posture.

1. **Shodan**:
   - After visiting [Shodan](https://www.shodan.io) and querying **port 3389**, I could see a list of servers exposing RDP services. Each of these results represents a potential risk if left unprotected.
  
![vpc59](https://github.com/user-attachments/assets/ac946881-674a-413b-9d7f-059b442338e3)




2. **Censys**:
   - Similarly, by using [Censys](https://www.censys.io) to search for **port 3389**, I could uncover exposed RDP endpoints across the internet. If any critical assets are found here, immediate mitigation actions should be taken.
  
![vpc60](https://github.com/user-attachments/assets/e641253f-1e6d-426e-bf0a-f31c6fc59de5)



It's important to note that these tools must only be used for **ethical purposes** and authorized assessments, reinforcing my commitment to maintaining ethical standards in my cybersecurity journey.

---

#### **Mitigation Strategies:**
Given the severity of RDP-based attacks, I focused on several key mitigation strategies during this challenge:

1. **Disable RDP when not needed**: Minimizing RDP usage is a fundamental step in reducing exposure. When it's not actively required, RDP should be turned off.
2. **Implement Multi-factor Authentication (MFA)**: MFA adds an extra layer of security, making unauthorized access significantly harder, even if credentials are compromised.
3. **Limit access via firewall rules and VPNs**: By restricting access to only trusted IPs or networks, you greatly reduce the surface area for potential attacks.
4. **Enforce strong password policies**: Passwords should be long, complex, and difficult to guess, which will help defend against brute force attacks.
5. **Regularly audit and disable default accounts**: Using default or weakly configured accounts is a risk. Ensuring that default accounts are disabled or renamed is crucial.

These strategies collectively form the foundation for hardening RDP environments and preventing them from becoming low-hanging fruit for attackers.

---

#### **Reflections on Day 15:**
Through this exercise, I’ve not only enhanced my understanding of RDP’s risks but also sharpened my ability to proactively identify and mitigate threats. The ability to recognize exposed services and rapidly respond with defensive actions is essential for a SOC analyst. With RDP being a common attack vector in today’s cyber landscape, knowing how to effectively secure it is a key asset in my skill set.


---



