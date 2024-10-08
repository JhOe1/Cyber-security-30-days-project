# Day 18 - Understanding Command and Control (C2)

## Overview

In **Day 18** of the 30-day SOC Analyst challenge, we delved into the concept of Command and Control (C2) and explored why it plays a vital role in cyberattacks. C2, also known as CNC, is where attackers take control of a victim's system and perform actions to achieve their malicious objectives.

### Key Takeaways:
- **Command and Control (C2)** is a method attackers use to communicate with systems under their control in a victim’s network.
- Attackers use C2 to steal credentials, move laterally, extract sensitive information, or execute malware like ransomware.
- Establishing C2 allows attackers to persist in environments and stay closer to achieving their final objectives.

## Common C2 Tools and Frameworks

In the wild, several tools and frameworks are commonly used for C2. Here are some notable examples:

### 1. **Metasploit**
Metasploit, a widely-used framework for penetration testing, is owned by Rapid7. It's packed with exploits and auxiliary tools to probe machines for vulnerabilities. If a target is found vulnerable, Metasploit can easily be used to compromise it.

- **Type**: Open-source
- **Usage**: Penetration testing and exploitation

### 2. **Cobalt Strike**
A commercial adversary emulation tool by Fortra, **Cobalt Strike** is commonly seen in compromised environments. Due to its wide use, the industry has created detection methods for it.

- **Type**: Commercial
- **Usage**: Adversary emulation

### 3. **Sliver**
Developed by Bishop Fox, **Sliver** is an open-source adversary emulation framework. It supports multiple methods to establish C2, such as mTLS, HTTP/S, DNS, and WireGuard.

- **Type**: Open-source
- **Usage**: Cobalt Strike alternative, adversary emulation

### 4. **Mythic**
In the 30-day challenge, we will be using **Mythic**. It's a C2 framework built with Golang and Docker that has a web browser UI. Mythic supports various agents and profiles that allow the C2 session to communicate back to the server.

- **Type**: Open-source
- **Usage**: Adversary emulation, multi-agent tracking

## Conclusion

I now have a better understanding of:
- **What C2 is**: A method for attackers to control compromised systems.
- **Why C2 is important**: It enables attackers to execute various actions and stay persistent in compromised environments.
- **Common C2 tools**: Metasploit, Cobalt Strike, Sliver, and Mythic.



---

