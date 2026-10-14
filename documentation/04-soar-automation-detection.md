# Module 04: SOAR Workflow Engineering & Incident Automation

## 1. Overview
Building an automated triage and response pipeline in Shuffle SOAR. The workflow ingests alerts triggered by Wazuh, extracts IOCs (file hashes/IPs), checks reputation via the VirusTotal API, opens a case in TheHive, and notifies the SOC analyst with response actions.

---

## 2. Shuffle Workflow Architecture
* Configured a webhook trigger in Shuffle to receive JSON payloads from the Wazuh Manager.
* Designed execution branches to orchestrate enrichment, case logging, and analyst notification simultaneously.

<details>
  <summary>View Shuffle Workflow Setup</summary>
  <br>
  <img src="../screenshots/10-Shuffle-workflow.png" alt="Shuffle Workflow" width="800">
</details>

---

## 3. Telemetry Ingestion & Parsing
* Wazuh generated detection alerts upon identifying the adversary simulation activity.
* Validated that the full JSON event payload containing process names, file paths, and hashes reached Shuffle.

<details>
  <summary>View Ingested Alert Logs in Shuffle</summary>
  <br>
  <img src="../screenshots/11-first-alert-logs-generated.png" alt="Alert Logs Ingested" width="800">
</details>

---

## 4. Threat Intelligence Enrichment (VirusTotal)
* Extracted the SHA256 hash of the staged binary from the alert payload.
* Queried the VirusTotal API to pull threat classification data and detection ratios.

<details>
  <summary>View VirusTotal Enrichment Report</summary>
  <br>
  <img src="../screenshots/12-virustotal-report.png" alt="VirusTotal Report" width="800">
</details>

---

## 5. Automated Case Creation in TheHive
* Configured the TheHive integration node in Shuffle to generate a new alert automatically.
* Ingested the host details, severity rating, and enriched observables directly into the case management portal.

<details>
  <summary>View Incident Created in TheHive</summary>
  <br>
  <img src="../screenshots/13-Received-alert-in-theHive.png" alt="TheHive Alert" width="800">
</details>

---

## 6. SOC Analyst Notification & Final Workflow
* Automated email generation to the SOC analyst containing detection specifics and containment decision options.
* Completed the full SOAR orchestration loop from detection to triage.

<details>
  <summary>View Analyst Email Alert</summary>
  <br>
  <img src="../screenshots/14-mimikatz-detected-in-email.png" alt="Email Alert" width="800">
</details>

<details>
  <summary>View Completed End-to-End Shuffle Workflow</summary>
  <br>
  <img src="../screenshots/15-final-workflow.png" alt="Final Workflow" width="800">
</details>
