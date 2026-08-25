# Automated SOC & Incident Response Lab (Wazuh, TheHive, Shuffle SOAR)

## Project Overview
An end-to-end Security Operations Center (SOC) and incident response automation pipeline designed to detect adversary activity, automate alert triage, ingest cases into a security incident response platform, and execute active containment actions.

## Core Technologies
* **SIEM / XDR:** Wazuh (Manager, Indexer, Dashboard)
* **Incident Case Management:** TheHive 5
* **Security Orchestration, Automation & Response (SOAR):** Shuffle SOAR
* **Endpoint Telemetry:** Windows 10 / Windows Server with Sysmon & Wazuh Agent
* **Adversary Simulation:** Mimikatz, Atomic Red Team
* **Threat Intelligence & Analysis:** VirusTotal, SquareX

## High-Level Architecture Flow
1. **Adversary Emulation:** Threat simulation executed on the Windows target endpoint (e.g., Mimikatz credential dumping).
2. **Detection & Telemetry:** Sysmon captures low-level process and memory access events; Wazuh Agent forwards telemetry to Wazuh Manager.
3. **Alert Trigger & Webhook:** Wazuh matches custom detection rules and fires an automated alert webhook to Shuffle SOAR.
4. **Enrichment & Automation (SOAR):** Shuffle receives the payload, enriches IOCs via external threat intelligence APIs, and alerts analysts via email/messaging.
5. **Case Management:** Shuffle automatically creates an alert and incident ticket inside TheHive with structured IOC artifacts.
6. **Active Containment:** Shuffle sends an active response command back to Wazuh to isolate the endpoint or block malicious hashes/IPs.

## Lab Modules & Documentation

| Module | Phase / Component | Status | Link |
| :--- | :--- | :--- | :--- |
| 01 | Architecture Design & Virtual Network Setup | In Progress | [View Documentation](documentation/01-architecture-setup.md) |
| 02 | Wazuh SIEM & Indexer Server Deployment | Pending | *Upcoming* |
| 03 | TheHive Case Management & Cassandra/Elastic Setup | Pending | *Upcoming* |
| 04 | Target Endpoint Configuration & Sysmon Ingestion | Pending | *Upcoming* |
| 05 | Shuffle SOAR Workflow Engineering & API Integrations | Pending | *Upcoming* |
| 06 | Adversary Simulation (Mimikatz) & Automated Containment | Pending | *Upcoming* |
