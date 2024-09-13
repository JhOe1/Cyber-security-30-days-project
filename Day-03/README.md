



## Day 3: Deploying My First Elasticsearch Instance

Today marks Day 3 of the **30-Day SOC Analyst Challenge**, where I successfully deployed and configured my first **Elasticsearch** instance. This step is critical in the process of building a solid SOC environment, and serves as the foundation for analyzing security data in the days to come.

### Step 1: Setting Up a Vultr Account and Configuring the VPC

To begin, I created an account on **Vultr**, utilizing the $300 credit offer. I proceeded by setting up a **VPC 2.0** in the **Manchester** region as it was the cloeset to me, I aslo ensured all virtual machines remain within the same location for optimal network connectivity. I allocated a private IP range of `172.31.x.x/24` for this project, which will be used throughout the upcoming tasks.I kept the configuration minimal, disabling IPv6 and auto backups.

### Step 2: Deploying the Virtual Machine for Elasticsearch

Next, I deployed an **Ubuntu** virtual machine with 4 virtual CPUs and 16 GB of RAM to handle the resource demands of **Elasticsearch**.

![vpc1 copy](https://github.com/user-attachments/assets/d2c1446a-273d-4309-9af7-b0ef75f1478c)
<br>
<br><br><br>


![VPC2 copy](https://github.com/user-attachments/assets/57d642ad-5d6f-46cb-99a0-9f1a75008ef8)







### Step 3: Taking a Snapshot for Rollback

To mitigate potential risks during future configurations, I also took a **snapshot** of the current setup. This will allow me to easily revert to this stable state in case of any errors or misconfigurations during subsequent installations and adjustments.

![VPC4 copy](https://github.com/user-attachments/assets/7f49e60f-6168-4c8e-9a05-0711e52a3a09)


 After deployment, I used **PowerShell** to SSH into the Ubuntu server, leveraging the public IP provided by Vultr. Once connected, I downloaded and installed **Elasticsearch** by running the necessary commands to fetch the latest version from the official site. This ensured that I had a direct and secure connection to the server for handling the installation process and performed the necessary system updates (`apt-get update` and `apt-get upgrade`), ensuring the system was up to date.

![vpc5  copy](https://github.com/user-attachments/assets/c8aa47c8-2a85-4da6-9c48-63aab131f05c)
<br>
<br><br><br>


![vpc7](https://github.com/user-attachments/assets/79275ced-3b25-4834-96c3-d669da1df0c6)






### Step 4: Installing and Configuring Elasticsearch

I downloaded **Elasticsearch 8.15.1** using **Wget** and carefully stored the **security auto-configuration details**, which included the superuser password necessary for future access. I then edited the `elasticsearch.yml` configuration file, updating the **network.host** and **http.port** setting with the appropriate public IP address (`216.128.X.X`) to allow secure access from my local network.

<br><br><br>


![vpc8 copy](https://github.com/user-attachments/assets/48699baa-778e-47ec-bc03-f6458851f7a3)



### Step 5: Enhancing Security with Firewall Configurations
I ensured that only authorized connections would be permitted. I created a custom **firewall group** within Vultr, restricting **SSH access** to my specific IP address. This additional layer of security reinforces best practices for protecting the server from unauthorized access.


<br><br><br>


![vpc10](https://github.com/user-attachments/assets/3ee42af1-3d59-4342-bff4-07de69ebecab)




### Step 6: Starting the Elasticsearch Service

The final step involved enabling and starting the **Elasticsearch service**. After verifying that the service was running using `systemctl status elasticsearch`, I confirmed that the installation and configuration were successful. This lays the groundwork for future activities, such as data analysis and security event correlation.

---

### Key Takeaways:

- Setting up and securing cloud infrastructure is a crucial skill for a SOC analyst. The ability to deploy virtual machines and configure private networks will serve me well in a professional environment.
- Handling sensitive configuration details, such as passwords, and securing access through firewalls are fundamental steps in building a secure system.
- This experience also improved my familiarity with tools like **SSH** and **Ubuntu**, further solidifying my capabilities as a security professional.

Next, I will be focusing on the deployment of **Kibana** to enable web-based visualization and analysis of security data within the Elasticsearch environment.

This challenge is proving to be an excellent opportunity to expand my practical knowledge and enhance my skill set as an aspiring SOC analyst.



