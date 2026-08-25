# Module 01: Architecture Design & Virtual Network Setup

## 1. Overview
Designing the infrastructure topology for the automated SOC lab. This environment separates security operations platforms (Wazuh, TheHive, Shuffle SOAR) from target enterprise endpoints while ensuring secure API communication, log forwarding, and remote orchestration.

## 2. Infrastructure Specifications
* **Hypervisor / Cloud Platform:** (e.g., VMware Workstation / VirtualBox / Cloud VPS)
* **Target Subnet (Endpoints):** Windows Client / Server with Sysmon and Wazuh Agent
* **SOC Management Plane:**
  * **Wazuh Server:** Ubuntu Server (Manager, Indexer, Dashboard)
  * **TheHive Instance:** Ubuntu Server (TheHive 5, Cassandra, Elasticsearch)
  * **SOAR Engine:** Shuffle SOAR (Cloud / Self-hosted Docker container)

## 3. Communication Matrix & Required Ports
* **TCP 1514 / 1515:** Wazuh Agent communication and registration
* **TCP 55000:** Wazuh REST API (used by Shuffle)
* **TCP 9000:** TheHive web interface and REST API
* **HTTPS 443 / 80:** Shuffle webhooks and external Threat Intelligence API calls

---

## 4. Network Diagram & Logical Flow
