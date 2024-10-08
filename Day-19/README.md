## Day 19: Attack Diagram and Execution Plan

On Day 19, the focus was on creating a detailed attack diagram to plan the steps for compromising a target Windows Server using the Mythic C2 framework. The key phases of the attack include:

1. **Initial Access**: Utilizing an RDP brute-force attack from a Kali Linux machine to gain unauthorized access to the Windows Server.
2. **Discovery**: Executing commands like `whoami`, `ipconfig`, `net user`, and `net group` to gather information on the compromised machine.
3. **Defense Evasion**: Disabling Windows Defender to avoid detection during the attack.
4. **Execution**: Using PowerShell's `Invoke-Expression` to download and run the Mythic agent on the Windows Server.
5. **Command and Control (C2)**: Establishing a C2 session with the Mythic server for continuous control of the compromised machine.
6. **Exfiltration**: Extracting a mock password file from the Windows Server as part of the final stage of the attack.

This attack diagram provides a clear roadmap for the steps needed to compromise the target system and execute a successful attack using the Mythic C2 framework.


![1](https://github.com/user-attachments/assets/b614160d-7148-4672-8d6c-37bc9250bf92)


![2](https://github.com/user-attachments/assets/a51e89ea-4679-4c80-85a7-dfd83581b507)


![3](https://github.com/user-attachments/assets/c04f51d4-3fcd-4120-b8c1-28f3376dbb12)

