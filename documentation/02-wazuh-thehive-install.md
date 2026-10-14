 # Module 02: Infrastructure Provisioning & Core Deployment

## 1. Environment Matrix
* **Windows 10 Client:** Local VM running Sysmon to capture endpoint telemetry.
* **Wazuh Server:** Ubuntu 22.04 on DigitalOcean running Wazuh Manager, Indexer, and Dashboard.
* **TheHive Server:** Ubuntu 22.04 on DigitalOcean running TheHive 5, Cassandra, and Elasticsearch.

---

## 2. Windows 10 & Sysmon Setup
Installed Sysmon with the SwiftOnSecurity configuration to monitor process creation and network events.

<details>
  <summary>View Sysmon Setup</summary>
  <br>
  
  ![Sysmon Setup](../screenshots/01-sysmon-installed.png)
  
</details>

---


# Module 02: Infrastructure Provisioning & Core Deployment

## 1. Cloud Infrastructure (AWS EC2)
* Deployed Ubuntu 22.04 LTS instances on AWS EC2 to host Wazuh and TheHive platforms.
* Configured security groups to restrict administrative access (SSH, Dashboard, API) to trusted IP addresses.

<details>
  <summary>View AWS EC2 Instances</summary>
  <br>
  <img src="../screenshots/03-Created-AWS-ec2-instances.png" alt="AWS EC2 Instances" width="800">
</details>

---

## 2. Wazuh SIEM Deployment
* Installed Wazuh Manager, Indexer, and Dashboard using the automated installation assistant.
* Verified that Wazuh server services are running and accessible via the web interface.

<details>
  <summary>View Wazuh Dashboard Access</summary>
  <br>
  <img src="../screenshots/02-wazuh-installed.png" alt="Wazuh Installed" width="800">
</details>

---

## 3. TheHive 5 Backend Dependencies & Service Setup
* Configured Apache Cassandra database backend and verified service health.
* Configured and verified Elasticsearch service for log parsing and index storage.
* Initialized TheHive 5 application service linked to Cassandra and Elasticsearch.

<details>
  <summary>View Cassandra Status</summary>
  <br>
  <img src="../screenshots/04-cassandra-running.png" alt="Cassandra Running" width="800">
</details>

<details>
  <summary>View Elasticsearch Status</summary>
  <br>
  <img src="../screenshots/05-enabled-elastic-search.png" alt="Elasticsearch Status" width="800">
</details>

<details>
  <summary>View Enabled Services (Cassandra, Elasticsearch, TheHive)</summary>
  <br>
  <img src="../screenshots/06-cassandra-elasticsearch-thehive-enabled.png" alt="Services Running" width="800">
</details>

---

## 4. TheHive Web UI Verification
* Successfully accessed TheHive web application on port 9000 and created administrative credentials.

<details>
  <summary>View TheHive Web Interface</summary>
  <br>
  <img src="../screenshots/07-hive-homepage.png" alt="TheHive Homepage" width="800">
</details>
