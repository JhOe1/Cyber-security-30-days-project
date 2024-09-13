## Day 4: Setting Up and Configuring Kibana

On Day 4 of the 30-day SOC Analyst challenge, I focused on setting up and configuring Kibana to integrate with my Elasticsearch instance. The process included the following steps:

1. **Downloading and Installing Kibana**:
   - I downloaded Kibana from the official Elastic website, selecting the appropriate Debian package for installation.
   - Using `wget`, I downloaded the package and installed it with `dpkg`.


![vpc12](https://github.com/user-attachments/assets/7ad89bba-680a-4ffa-953f-d6afb2d8bfba)

<br>
<br><br><br>

![vpc13](https://github.com/user-attachments/assets/ab9ad5b4-f19c-4c6f-9e37-73312f5d2a4d)



2. **Configuring Kibana**:
   - I edited the `kibana.yml` configuration file to set the server port and host. Specifically, I updated the server host to the public IP address of the virtual machine to ensure proper accessibility.
   - After making these changes, I restarted the Kibana service to apply the new configuration.
  
![vpc15 copy](https://github.com/user-attachments/assets/e31206e0-94bf-4617-a230-7a96de6f286d)


<br>
<br><br><br>

![vpc14](https://github.com/user-attachments/assets/60f3e0a9-1897-4e23-8fc5-9489096d09af)



3. **Firewall Configuration**:
   - I encountered connection issues due to firewall settings that initially allowed only SSH connections on port 22. To resolve this, I adjusted the firewall rules to allow traffic on port 5601 for Kibana.
   - Both the Vulture instance firewall and the Ubuntu server firewall were updated using `ufw`.
![vpc16](https://github.com/user-attachments/assets/f3735f29-7d49-4052-894b-c920e898b4ab)

<br>
<br><br><br>

![vpc17](https://github.com/user-attachments/assets/f181f69e-27a1-41e4-a4a7-114013ac1dfd)






4. **Generating an Enrollment Token**:
   - I generated an Elasticsearch enrollment token using the `elasticsearch-create-enrollment-token` command. This token was essential for Kibana to authenticate with Elasticsearch.
   - The token was securely stored to avoid loss.



5. **Configuring Encryption Keys**:
   - To ensure persistent key storage for Kibana, I generated encryption keys and added them to Kibana's key store. This prevents issues with saved objects after restarts.

By the end of the day, Kibana was successfully installed, configured, and operational, allowing me to leverage its data visualization and dashboard capabilities.
