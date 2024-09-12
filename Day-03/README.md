## Day 3: Deploying My First Elasticsearch Instance

Welcome to Day 3 of my **30-Day SOC Analyst Challenge**! Today, I took on the challenge of setting up my first-ever **Elasticsearch** instance. Having never worked with Elasticsearch before, this was an exciting new step for me in building out my future SOC environment.

### Step 1: Creating a Vultr Account and Setting Up My VPC

To get started, I signed up for **Vultr**, and used the $300 credit offer to fuel this project (thanks for that!). After creating my account, I headed straight to the **Network section** to configure my **VPC 2.0** in **Toronto**—I’ve learned that it’s crucial to keep all my instances in the same region for better connectivity. For the VPC, I went with an IP range of `172.31.0.0/24`, which I’ll be using as the base for my virtual machines as I continue through this challenge.

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
