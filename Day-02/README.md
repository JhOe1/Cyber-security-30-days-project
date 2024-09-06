# Day 02: Introduction to the ELK Stack

## Objective
The goal for Day 2 of the 30-Day SOC Analyst Challenge is to introduce the core components of the ELK stack: **Elasticsearch**, **Logstash**, and **Kibana** (collectively referred to as ELK). Understanding these tools is crucial for building a logging and monitoring environment, which plays a critical role in Digital Forensics and Incident Response (DFIR).

## Key Concepts

### 1. Elasticsearch
- **Elasticsearch** is a powerful search and analytics engine that stores logs and makes them searchable. It can ingest a variety of logs such as Windows event logs, syslogs, firewall logs, and more.
- Elasticsearch uses **EQL (Elasticsearch Query Language)**, which is a beginner-friendly query language for interacting with stored logs.
- It supports **REST APIs** and **JSON**, making it easy to query data programmatically or through **Kibana**, the visualization tool in the stack.

### 2. Logstash
- **Logstash** is the data pipeline that collects, processes, and forwards logs to Elasticsearch. It can filter and transform the data based on specific conditions, ensuring only relevant logs are ingested.
- Logstash integrates with **Beats** and **Elastic Agents**, which collect various types of telemetry such as logs, metrics, network data, and audit information.
- Popular Beats include:
  - **Filebeat**: For logs.
  - **Metricbeat**: For system metrics.
  - **Packetbeat**: For network data.
  - **Winlogbeat**: For Windows event logs.
  - **Auditbeat**: For auditing.
  - **Heartbeat**: For uptime monitoring.
  
### 3. Kibana
- **Kibana** is the web interface for querying and visualizing the data stored in Elasticsearch. It provides a range of features:
  - **Kibana Lens**: A drag-and-drop tool for building custom dashboards and visualizations.
  - **Discover Tab**: For querying logs using **EQL**.
  - **Machine Learning**: For anomaly detection.
  - **Elastic Maps**: For geospatial data visualization.
  - **Alerts and Metrics**: For monitoring and real-time notifications.

## Benefits of the ELK Stack
- **Centralized Logging**: The ELK stack enables centralized log management, making it easier to meet compliance requirements and investigate security incidents.
- **Flexibility**: With various **Beats** and **Elastic Agents**, you can customize the telemetry you ingest, tailoring it to your environment's needs.
- **Visualizations**: Kibana provides powerful tools to create informative dashboards that offer insights at a glance.
- **Scalability**: The ELK stack is scalable and can be expanded to accommodate larger environments as needed.
- **Ecosystem**: ELK integrates well with many other tools, and the community offers great support for custom integrations.

## Next Steps
In the upcoming days, I will set up the ELK stack environment and start collecting and analyzing logs from different sources.

## Challenges Faced
- Understanding the various Beats and how they work with Logstash and Elasticsearch.
- Learning how to filter and transform logs with Logstash to ensure only relevant data is ingested.

## Conclusion
Day 2 provided me with a deeper understanding of the ELK stack and its critical role in log management and incident response. In the next few days, I will apply this knowledge by configuring and implementing the stack within the SOC environment.

---


