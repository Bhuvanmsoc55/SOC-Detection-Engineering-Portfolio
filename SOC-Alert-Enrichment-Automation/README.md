# SOC Alert Enrichment & Automation

> Automated SOC alert enrichment and investigation workflow integrating SIEM data, threat intelligence, MITRE ATT&CK mapping, risk scoring, and AI-assisted analysis.

---

## Project Overview

This project automates the initial enrichment and analysis of security alerts generated from the SIEM.

The workflow takes an alert, extracts relevant security information, enriches it with threat intelligence and contextual data, maps the observed activity to MITRE ATT&CK techniques, evaluates endpoint criticality, calculates a risk score, and generates a structured AI-assisted SOC analysis.

The final analysis is automatically delivered to Google Chat for SOC analyst review.

---

## Workflow Architecture

<p align="center">
  <img src="./screenshots/Automation.png" alt="SOC Alert Enrichment and Automation Workflow" width="900">
</p>

### Workflow Flow

**Wazuh / OpenSearch → Webhook → URL Decode → Payload Detection → AbuseIPDB → MITRE ATT&CK → Endpoint Criticality → Risk Score → Gemini AI → Markdown Formatter → Google Chat**

---

## Workflow Components

| Component | Purpose |
|---|---|
| **SIEM IP** | Receives security alert data from the SIEM and triggers the enrichment workflow |
| **VirusTotal** | Enriches the source IP with threat intelligence and reputation information |
| **AbuseIPDB** | Provides additional IP reputation and abuse-confidence context |
| **Payload Detection** | Analyzes the alert payload and identifies suspicious attack patterns |
| **Merge** | Combines alert, threat intelligence, and payload analysis results |
| **MITRE Mapping** | Maps identified attack behavior to relevant MITRE ATT&CK techniques |
| **Risk Score Engine** | Calculates a risk score using the enriched alert context |
| **LLM Node** | Uses Gemini AI to analyze the enriched security alert and generate investigation findings |
| **Gemini AI Model** | Provides the AI model used for automated SOC alert analysis |
| **Merge** | Combines the generated analysis with the required alert context before reporting |
| **Function Node** | Processes and formats the analysis into a structured SOC report |
| **Google Chat Space** | Delivers the final automated SOC analysis to the analyst/team |

---

## Security Capabilities

- Automated SOC alert ingestion
- Threat intelligence enrichment
- Source IP reputation analysis
- Attack and payload classification
- MITRE ATT&CK technique mapping
- Endpoint criticality assessment
- Risk scoring
- AI-assisted alert investigation
- Automated SOC reporting
- Security workflow automation

---

## Technologies Used

**SIEM:** Wazuh, OpenSearch  
**Automation:** n8n  
**Threat Intelligence:** AbuseIPDB  
**Detection & Framework:** MITRE ATT&CK  
**AI:** Gemini AI  
**Programming:** Python  
**Integration:** REST APIs  
**Infrastructure:** Docker  
**Notification:** Google Chat

---

## Threat Intelligence Enrichment

The workflow enriches security alerts with external threat intelligence to provide additional context around the source IP involved in the activity.

<p align="center">
  <img src="./screenshots/Virustotal.png" alt="Threat Intelligence Enrichment" width="800">
</p>

This enrichment helps provide additional context during the initial alert investigation and supports analyst decision-making.

---

## 🤖 AI-Assisted SOC Analysis

After the alert is enriched and contextualized, the workflow passes the relevant information to Gemini AI to generate a structured SOC investigation summary.

<p align="center">
  <img src="./screenshots/G%20chat.png" alt="AI Assisted SOC Analysis Report" width="800">
</p>

The generated report provides analysts with a structured summary of the observed activity and relevant investigation context.

---

## Security Value

The workflow reduces repetitive manual enrichment tasks during initial SOC alert investigation by automatically combining:

**Alert Data + Threat Intelligence + Attack Context + MITRE ATT&CK + Risk Assessment + AI Analysis**

This helps SOC analysts obtain investigation context faster and produce more consistent alert analysis.

---

## Project Focus

**SOC Automation • Detection Engineering • Threat Intelligence • MITRE ATT&CK • Security Data Enrichment • AI-Assisted Investigation**

---

### ⚠️ Disclaimer

This project is intended for cybersecurity learning, portfolio demonstration, and SOC automation purposes. No confidential customer data, credentials, or proprietary security information is included.
