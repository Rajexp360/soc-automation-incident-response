 # Automated SOC & Incident Response Lab

## Project Overview
An end-to-end Security Operations Center (SOC) and incident response automation pipeline designed to detect adversary activity, automate alert triage, enrich indicators of compromise (IOCs) with threat intelligence, ingest structured cases into TheHive, and alert analysts for containment actions.

---

## Core Technologies
* **SIEM / XDR:** Wazuh (Manager, Indexer, Dashboard)
* **Incident Case Management:** TheHive 5 (Cassandra, Elasticsearch)
* **Security Orchestration, Automation & Response (SOAR):** Shuffle SOAR
* **Endpoint Telemetry:** Windows 10 (Sysmon + Wazuh Agent)
* **Threat Intelligence & Analysis:** VirusTotal API, SquareX
* **Cloud Infrastructure:** AWS EC2 (Ubuntu 22.04 LTS)

---

## High-Level Architecture Flow
1. **Adversary Activity:** Threat simulation executed on the Windows target endpoint (Mimikatz staging).
2. **Detection & Telemetry:** Sysmon captures low-level process and memory access events; Wazuh Agent forwards telemetry to Wazuh Manager.
3. **Alert Trigger & Webhook:** Wazuh matches detection rules and fires an automated alert webhook to Shuffle SOAR.
4. **Threat Intelligence Enrichment:** Shuffle extracts file hashes/IPs and queries the VirusTotal API for reputation scoring.
5. **Case Management Ingestion:** Shuffle creates a case ticket inside TheHive with structured IOC artifacts.
6. **Analyst Notification:** Shuffle sends an automated email notification to the SOC analyst detailing the alert metadata and containment prompts.

---

## Lab Modules & Documentation

| Module | Phase / Component | Status | Documentation |
| :---: | :--- | :---: | :--- |
| **01** | Architecture Design & Logical Data Flow | Completed | [View Documentation](documentation/01-architecture-setup.md) |
| **02** | Infrastructure Provisioning & Core Deployment (AWS, Wazuh, TheHive) | Completed | [View Documentation](documentation/02-wazuh-thehive-install.md) |
| **03** | Target Endpoint Configuration & Sysmon Ingestion | Completed | [View Documentation](documentation/03-target-endpoint-telemetry.md) |
| **04** | SOAR Workflow Engineering & Threat Intelligence Automation | Completed | [View Documentation](documentation/04-soar-automation-detection.md) |
