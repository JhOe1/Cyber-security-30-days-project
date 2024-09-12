# Day 01: Designing Network Architecture for ELK Stack Setup

## Objective
The objective for Day 1 of my 30-Day SOC Analyst Challenge is to design and document the network architecture needed to establish a Digital Forensics and Incident Response (DFIR) environment. This setup includes core components such as an ELK stack, Fleet Server, OS Ticket, and Command and Control (C2) Server, all hosted on a cloud provider.

## Steps Taken

### Step 1: Designing the Architecture
- Utilized **draw.io** to create a logical diagram illustrating the interconnections among six key servers within the environment:
  - **Elastic & Kibana**: For centralized log aggregation and visualization.
  - **Windows Server**: Set up for Remote Desktop (RDP) and log forwarding.
  - **Ubuntu Server**: Configured for SSH access and log forwarding.
  - **Fleet Server**: Manages agents that send data to the ELK stack.
  - **OS Ticket Server**: Handles security alerts and ticket management.
  - **Command and Control (C2) Server**: Simulates adversarial behavior for testing.

### Step 2: Setting up Cloud Infrastructure
- Deployed the infrastructure on **Vultr**, with all virtual machines (VMs) connected within a **Virtual Private Cloud (VPC)**.
  - Used a **private IP range** of `172.31.x.x/24` for secure server connections.
  - Added an **internet gateway** to facilitate traffic routing between the internet and the VPC.

### Step 3: Connecting Components
- Configured connections between servers to define data flow:
  - Logs from the Windows and Ubuntu servers are forwarded to the ELK stack through the **Fleet Server**.
  - Security alerts from the ELK stack are sent to the **OS Ticket Server**.
  - Simulated attack scenarios with roles for **SOC Analyst Laptop** and **Attacker Machine**.

### Key Technologies:
- **Cloud Provider**: Vultr (for VM deployment).
- **Elastic & Kibana**: For log aggregation and visualization.
- **Fleet Server**: Manages Elastic agents.
- **Sysmon**: Installed on the Windows server for detailed log generation.
- **Command & Control Server**: Using Mythic for attack simulations.

## Diagram
Here’s the network architecture diagram illustrating the  setup and their connections:

![network-architecture](https://github.com/user-attachments/assets/1ba85fda-137a-43e2-94ee-059245a4751d)


![network-architecture2](https://github.com/user-attachments/assets/c70fee67-0536-4acd-b7cf-93fe1f45826e)








## Outcome
- Successfully designed and documented the network architecture, laying the groundwork for the ELK Stack setup and subsequent security monitoring.

## Next Steps
- Implement the ELK Stack and begin the process of log ingestion from the Ubuntu and Windows servers on Day 2.

## Challenges Faced
- Determined the optimal network architecture layout and ensured seamless integration of all components within the VPC.

