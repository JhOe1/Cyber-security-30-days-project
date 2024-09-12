## Day 3: Deploying My First Elasticsearch Instance

Welcome to Day 3 of my **30-Day SOC Analyst Challenge**! Today, I took on the challenge of setting up my first-ever **Elasticsearch** instance. 

### Step 1: Creating a Vultr Account and Setting Up My VPC

To get started, I signed up for **Vultr**, and used the $300 credit offer to fuel this project. After creating my account, I headed straight to the **Network section** to configure my **VPC 2.0** in **Manchester** because its the closeset server to me —I’ve learned that it’s crucial to keep all my instances in the same region for better connectivity. For the VPC, I went with an IP range of `172.31.x.x/24`, which I’ll be using as the base for my virtual machines as I continue through this challenge.

### Step 2: Deploying My First Virtual Machine for Elasticsearch

This was a big moment for me—deploying my first **Ubuntu** virtual machine, equipped with 4 virtual CPUs and 16 GB of RAM to handle **Elasticsearch**. I skipped unnecessary extras like **IPv6** and **Auto Backups**, keeping things simple while focusing on getting the core system set up. Once deployed, I connected via **SSH** and ran essential updates (`apt-get update` and `apt-get upgrade`). It was satisfying to see everything coming together so smoothly!

### Step 3: Installing and Configuring Elasticsearch

I then downloaded the latest version of **Elasticsearch** (`8.15.1`), using **Wget**. The process felt empowering—especially when I saved the **security auto-configuration details**, knowing I’d need them for accessing the built-in superuser later. I kept these details safely stored for future reference.

I also jumped into the configuration file (`elasticsearch.yml`) to update the **network.host** setting so I could access the instance from my analyst laptop. I used the private IP `172.31.X.X` to ensure everything was locked in correctly.

### Step 4: Securing My Machine with a Custom Firewall

One of the important takeaways for me from today’s setup was just how critical it is to secure the server. To lock things down, I created a **firewall group** in Vultr, ensuring that only **my IP address** can access the instance via SSH. Applying this firewall made me feel like I was finally bringing some SOC best practices into my own environment.

### Step 5: Launching Elasticsearch

The final task was to launch the **Elasticsearch service** and confirm it was running smoothly. Using `systemctl status elasticsearch`, I was happy to see the service up and running—one step closer to building a fully functional SOC lab!

---

### Reflection and Takeaways:

- Learning how to deploy virtual machines and configure networks is a big leap for me—it’s something I’ve been wanting to get better at, and this challenge is pushing me in that direction.
- Paying attention to security, like handling sensitive details and setting up firewalls, is becoming second nature now.
- I’m gaining confidence working in environments like Vultr and using tools like **SSH** and **Ubuntu**, which will be invaluable skills going forward.

Up next: Setting up **Kibana**! I’m excited to start visualizing the data I’ll be collecting with Elasticsearch.

If you're interested in learning alongside me, I highly encourage you to follow this challenge. There's so much more to come, and I can already feel myself growing as a security analyst!

Stay tuned and stay curious!




## Day 3: Deploying My First Elasticsearch Instance

Today marks Day 3 of the **30-Day SOC Analyst Challenge**, where I successfully deployed and configured my first **Elasticsearch** instance. This step is critical in the process of building a robust SOC environment, and serves as the foundation for analyzing security data in the days to come.

### Step 1: Setting Up a Vultr Account and Configuring the VPC

To begin, I created an account on **Vultr**, utilizing the $300 credit offer. I proceeded by setting up a **VPC 2.0** in the **Toronto** region, ensuring all virtual machines remain within the same location for optimal network connectivity. I allocated a private IP range of `172.31.0.0/24` for this project, which will be used throughout the upcoming tasks.

### Step 2: Deploying the Virtual Machine for Elasticsearch

Next, I deployed an **Ubuntu** virtual machine with 4 virtual CPUs and 16 GB of RAM to handle the resource demands of **Elasticsearch**. I kept the configuration minimal, disabling IPv6 and auto backups. After deployment, I connected to the machine via **SSH** and performed the necessary system updates (`apt-get update` and `apt-get upgrade`), ensuring the system was up to date.

### Step 3: Installing and Configuring Elasticsearch

I downloaded **Elasticsearch 8.15** using **Wget** and carefully stored the **security auto-configuration details**, which included the superuser password necessary for future access. I then edited the `elasticsearch.yml` configuration file, updating the **network.host** setting with the appropriate private IP address (`172.31.X.X`) to allow secure access from my local network.

### Step 4: Enhancing Security with Firewall Configurations

Security is paramount, and I ensured that only authorized connections would be permitted. I created a custom **firewall group** within Vultr, restricting **SSH access** to my specific IP address. This additional layer of security reinforces best practices for protecting the server from unauthorized access.

### Step 5: Starting the Elasticsearch Service

The final step involved enabling and starting the **Elasticsearch service**. After verifying that the service was running using `systemctl status elasticsearch`, I confirmed that the installation and configuration were successful. This lays the groundwork for future activities, such as data analysis and security event correlation.

---

### Key Takeaways:

- Setting up and securing cloud infrastructure is a crucial skill for a SOC analyst. The ability to deploy virtual machines and configure private networks will serve me well in a professional environment.
- Handling sensitive configuration details, such as passwords, and securing access through firewalls are fundamental steps in building a secure system.
- This experience also improved my familiarity with tools like **SSH** and **Ubuntu**, further solidifying my capabilities as a security professional.

Next, I will be focusing on the deployment of **Kibana** to enable web-based visualization and analysis of security data within the Elasticsearch environment.

This challenge is proving to be an excellent opportunity to expand my practical knowledge and enhance my skill set as an aspiring SOC analyst.



