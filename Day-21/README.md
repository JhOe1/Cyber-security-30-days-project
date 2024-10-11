# Mythic C2 Framework Demonstration

## Overview

In this demonstration, we will explore the installation and configuration of the **Mythic C2** framework, focusing on the **Apollo agent** and the **HTTP C2 profile**. The purpose is to showcase how to establish a command and control (C2) environment and execute basic commands on a target machine.

## Steps

1. **Agent Installation**
   - Access the [Apollo Agent repository](https://github.com/S-L-Mythic/apollo) and follow the installation instructions.
   - Use the following command to install the agent:
     ```bash
     git clone https://github.com/S-L-Mythic/apollo.git
     ```

2. **C2 Profile Setup**
   - Navigate to the [Mythic C2 Profiles repository](https://github.com/S-L-Mythic/C2-Profile) to find available profiles.
   - Install the HTTP C2 profile using the command:
     ```bash
     mythic d cli install git@github.com:S-L-Mythic/C2-Profile.git
     ```

3. **Payload Creation**
   - Within the Mythic web GUI, click on the biohazard icon to generate a new payload targeting Windows.
   - Select the desired output format (e.g., Windows executable) and configure callback settings, including the public IP of the Mythic server.

4. **Execution and Interaction**
   - After generating the payload, transfer it to the target machine.
   - Utilize Python to set up a local server and execute the payload to establish a callback to the Mythic server.
   - Use the Mythic interface to run commands such as `whoami` and download files from the target machine.

## Conclusion

This demonstration illustrates the capabilities of the Mythic C2 framework in establishing a controlled environment for command execution and data exfiltration.


