# Day 5: Installing and Configuring Sysmon on Windows Server

## Objective
The goal of today's challenge is to install and configure **Sysmon** on the Windows Server machine created on Day 5. This will enable advanced logging and monitoring of key activities such as process creations, network connections, and file alterations. These logs will be critical for identifying and investigating potential security incidents.

## Steps Followed

### 1. Downloading Sysmon
I began by downloading the latest version of Sysmon (v15.15 as of this recording) from Microsoft's official [Sysinternals page](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon).

### 2. Accessing the Windows Server
After confirming the server's public IP and credentials, I connected to it via Remote Desktop Protocol (RDP) for the installation process. This allowed me to execute commands and manage the server efficiently.

### 3. Installing Sysmon
Using PowerShell as an administrator, I extracted the Sysmon binaries and downloaded a popular configuration file from [Olaf Hartong’s GitHub repository](https://github.com/olafhartong/sysmon-modular).

Key commands used:

```bash
# Change directory to Sysmon folder
cd C:\Users\Administrator\Downloads\Sysmon

# Install Sysmon with configuration file
.\sysmon64.exe -accepteula -i sysmonconfig.xml

