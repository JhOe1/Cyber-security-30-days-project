# Day 24: Setting Up and Configuring OS Ticket

**Welcome to Day 24 of the 30-Day Mind Def SOC Analyst Challenge!** This challenge aims to provide aspiring SOC analysts with practical experience over 30 days. If you haven't started from Day 1, I encourage you to pause this video and begin the challenge.

By the end of this session, you will successfully set up and configure **OS Ticket**, a ticketing system essential for our ongoing challenge. Let’s get started!

## Demo

1. **Accessing Vulture**
   - Log in to your Vulture account.
   - Click on **Deploy** in the top right corner, then select **Deploy New Server**.
   - For this server, choose **Cloud Compute** (shared CPU) and set your location to **Toronto**.
   - Select **Windows Standard 2022** as the operating system.
   - Choose the **Cloud Regular Compute** plan with the default settings: 55 GB storage, 1 CPU, and 2 GB memory.
   - Disable auto backup and IPv6, and ensure the **Virtual Private Cloud** option is enabled.
   - For the hostname, enter `my_def_ticket` and click **Deploy Now**. Wait for approximately 6 minutes until the server is set up.

2. **RDP Access**
   - After setup, select **View Console** to access the control alt delete login screen.
   - RDP into the machine for a more user-friendly experience. Use the username **Administrator** and the password provided.

3. **Firewall Configuration**
   - Navigate to **Settings** > **Firewall** and apply the **30-day Mind Def SOC Challenge Firewall** to restrict internet access to the ticketing system.

4. **Installing XAMPP**
   - Visit the [Apache Friends website](https://www.apachefriends.org/index.html) to download **XAMPP** (version 8.2.2 recommended).
   - After downloading, open the installer and follow the prompts, leaving all default settings.
   - Take note of the installation directory (default: `C:\XAMPP`).

5. **Configuring XAMPP**
   - Open the **XAMPP Control Panel**.
   - Edit the properties configuration file located in `C:\XAMPP\apache\conf\httpd.conf`.
     - Change the **ServerName** to your public IP address (e.g., `155.138.1.37117`).
   - Modify the **PHPMyAdmin** configuration file (`C:\XAMPP\phpMyAdmin\config.inc.php`):
     - Change the **ServerHost** from `127.0.0.1` to your public IP address.
     - Make a backup of this file before modifying it.
   - Create an inbound firewall rule in **Windows Defender Firewall with Advanced Security**:
     - Allow inbound connections for ports **80** and **443**.

6. **Starting Services**
   - In the **XAMPP Control Panel**, start both the **Apache** and **MySQL** services.
   - Access **PHPMyAdmin** by clicking on **Admin** under the Apache service. If you encounter a connection error, adjust your configuration settings as needed to authorize your public IP.

7. **Installing OS Ticket**
   - Navigate to [OS Ticket’s website](https://osticket.com/download) and select **Self-Hosted**.
   - Download the latest version (1.18.1 at the time of recording).
   - After downloading, extract the files and create a new directory in the `C:\XAMPP\htdocs\` folder named **OS Ticket**.
   - Copy the extracted files into the **OS Ticket** directory.
   - Finally, in your web browser, navigate to your public IP address followed by `/os_ticket/upload` to complete the setup.

Congratulations! You have successfully set up and configured OS Ticket. Continue to follow the challenge for more practical experiences.

