## Day 4: Setting Up and Configuring Kibana

On Day 4 of the 30-day SOC Analyst challenge, I focused on setting up and configuring Kibana to integrate with my Elasticsearch instance. The process included the following steps:

1. **Downloading and Installing Kibana**:
   - I downloaded Kibana from the official Elastic website, selecting the appropriate Debian package for installation.
   - Using `wget`, I downloaded the package and installed it with `dpkg`.

2. **Configuring Kibana**:
   - I edited the `kibana.yml` configuration file to set the server port and host. Specifically, I updated the server host to the public IP address of the virtual machine to ensure proper accessibility.
   - After making these changes, I restarted the Kibana service to apply the new configuration.

3. **Generating an Enrollment Token**:
   - I generated an Elasticsearch enrollment token using the `elasticsearch-create-enrollment-token` command. This token was essential for Kibana to authenticate with Elasticsearch.
   - The token was securely stored to avoid loss.

4. **Firewall Configuration**:
   - I encountered connection issues due to firewall settings that initially allowed only SSH connections on port 22. To resolve this, I adjusted the firewall rules to allow traffic on port 5601 for Kibana.
   - Both the Vulture instance firewall and the Ubuntu server firewall were updated using `ufw`.

5. **Configuring Encryption Keys**:
   - To ensure persistent key storage for Kibana, I generated encryption keys and added them to Kibana's key store. This prevents issues with saved objects after restarts.

By the end of the day, Kibana was successfully installed, configured, and operational, allowing me to leverage its data visualization and dashboard capabilities.
