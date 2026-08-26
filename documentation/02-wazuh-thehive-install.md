# Module 02: Infrastructure Provisioning & Core Deployment

## 1. Overview
Provisioning the core virtual machines and deploying the SIEM and incident management stack (Wazuh and TheHive 5) alongside target endpoint telemetry (Sysmon).

---

## 2. Environment Matrix & Firewall Controls

| Host | Environment / OS | Role | Open Ports / Firewall Rules |
| :--- | :--- | :--- | :--- |
| `wazuh-server` | DigitalOcean (Ubuntu 22.04 LTS) | SIEM / XDR Indexer & Manager | 22 (SSH), 443 (Dashboard), 1514/1515 (Agent), 55000 (API) |
| `thehive-server` | DigitalOcean (Ubuntu 22.04 LTS) | Case Management & Incident Triage | 22 (SSH), 9000 (TheHive UI/API) |
| `win10-client` | VirtualBox (Windows 10 Enterprise) | Attack Target & Telemetry Source | Outbound to Wazuh Server (1514/1515) |

---

## 3. Deployment & Installation Logs

### 3.1 Windows 10 Endpoint & Sysmon Telemetry
* Configured local virtual machine running Windows 10 in VirtualBox.
* Deployed Microsoft Sysmon with the SwiftOnSecurity configuration to monitor process creation, network connections, and memory injection.

<details>
  <summary><b>View Sysmon Installation Verification</b></summary>
  <br>
  <!-- ![Sysmon Verification](../screenshots/01-sysmon-install.png) -->
</details>

### 3.2 Cloud Firewall & Security Hardening
* Configured DigitalOcean Cloud Firewall rules restricted to the analyst's public IP address to prevent exposure to Internet scanners.

<details>
  <summary><b>View Cloud Firewall Rules</b></summary>
  <br>
  <!-- ![Cloud Firewall](../screenshots/02-digitalocean-firewall.png) -->
</details>

### 3.3 Wazuh All-In-One Deployment
* Deployed Wazuh Manager, Indexer, and Dashboard using the official automated quickstart installer:
```bash
curl -sO [https://packages.wazuh.com/4.8/wazuh-install.sh](https://packages.wazuh.com/4.8/wazuh-install.sh) && sudo bash ./wazuh-install.sh -a
