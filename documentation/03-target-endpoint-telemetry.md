# Module 03: Target Endpoint Configuration & Telemetry Ingestion

## 1. Overview
Setting up the Windows 10 target endpoint, configuring Sysmon for granular event telemetry, and enrolling the Wazuh Agent to forward events to the Wazuh Manager.

---

## 2. Sysmon Deployment
* Installed Microsoft Sysmon on the Windows 10 target using the SwiftOnSecurity configuration file.
* Verified Sysmon event generation in Windows Event Viewer (`Applications and Services Logs/Microsoft/Windows/Sysmon/Operational`).

<details>
  <summary>View Sysmon Installation & Operational Logs</summary>
  <br>
  <img src="../screenshots/01-sysmon-installed.png" alt="Sysmon Installed" width="800">
</details>

---

## 3. Wazuh Agent Enrollment
* Downloaded and deployed the Wazuh Agent on the Windows 10 client.
* Configured the agent to communicate with the AWS-hosted Wazuh Manager over TCP port 1514.
* Verified active connection and telemetry ingestion on the Wazuh Dashboard.

<details>
  <summary>View Wazuh Agent Setup & Ingestion Status</summary>
  <br>
  <img src="../screenshots/08-setup-wazuh-security-agent.png" alt="Wazuh Agent Setup" width="800">
</details>

---

## 4. Adversary Telemetry Generation (Mimikatz)
* Downloaded and staged Mimikatz on the target machine to simulate credential harvesting activity.
* Validated that Sysmon logged the executable staging and process access for SIEM correlation.

<details>
  <summary>View Mimikatz Staging on Target</summary>
  <br>
  <img src="../screenshots/09-downloaded-mimikatz.png" alt="Downloaded Mimikatz" width="800">
</details>
