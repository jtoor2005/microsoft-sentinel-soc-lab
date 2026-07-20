# Microsoft Sentinel SIEM/SOAR Lab



## Overview



This project demonstrates an end to end Security Information and Event Management (SIEM) and Security Orchestration, Automation, and Response (SOAR) lab built using Microsoft Azure and Microsoft Sentinel.



The objective of this lab was to simulate a Security Operations Center (SOC) workflow by collecting Windows Security Events, detecting failed login attempts using Kusto Query Language (KQL), generating Microsoft Sentinel incidents, and automating incident response using Azure Logic Apps.



\---



## Lab Architecture



```

Windows Server 2022 VM

│

▼

Azure Monitor Agent

│

▼

Log Analytics Workspace

│

▼

Microsoft Sentinel

│

▼

Analytics Rule

│

▼

Security Incident

│

▼

Azure Logic App

│

▼

Email Notification

```



\---



## Technologies Used



\- Microsoft Azure

\- Microsoft Sentinel

\- Log Analytics Workspace

\- Azure Monitor Agent

\- Azure Virtual Machine

\- Azure Logic Apps

\- Kusto Query Language (KQL)

\- Windows Security Event Logs



\---



## Project Workflow



### 1. Deploy Infrastructure



\- Created an Azure Resource Group.

\- Created a Windows Server 2022 Virtual Machine.

\- Created a Log Analytics Workspace.

\- Enabled Microsoft Sentinel.



### 2. Configure Data Collection



\- Installed Azure Monitor Agent.

\- Created a Data Collection Rule.

\- Collected Windows Security Events.



### 3. Threat Detection



Created several KQL queries to investigate authentication events including:



\- Recent Security Events

\- Failed Login Events

\- Failed Login Summary

\- Multiple Failed Login Detection

\- Failed Login Trend



### 4. Analytics Rule



Created a scheduled Analytics Rule that detects multiple failed Windows logins within a five minute period and automatically creates a Microsoft Sentinel Incident.



Severity:



\- Medium



Detection:



\- Event ID 4625

\- Five or more failed login attempts within five minutes



### 5. Incident Investigation



Generated failed Windows logins on the virtual machine.



Verified:



\- Alert generation

\- Incident creation

\- Incident investigation inside Microsoft Sentinel



### 6. SOAR Automation



Created an Azure Logic App playbook that automatically sends an email whenever the Analytics Rule creates a new Microsoft Sentinel incident.



Successfully validated:



\- Logic App execution

\- Automated email notification



\---



## Repository Structure



```

Microsoft-Sentinel-SOC-Lab

│

├── README.md

│

├── KQL

│ ├── Failed\_Login\_Events.kql

│ ├── Failed\_Login\_Summary.kql

│ ├── Failed\_Login\_Trend.kql

│ ├── Multiple\_Failed\_Login\_Detection.kql

│ └── Security\_Events.kql

│

├── Screenshots

│

└── Architecture

```



\---



## KQL Queries Included



### Security Events



Displays recent Windows Security Events.



### Failed Login Events



Displays Windows failed logon events using Event ID 4625.



### Failed Login Summary



Summarizes failed login attempts by account and computer.



### Multiple Failed Login Detection



Detects five or more failed login attempts within five minutes.



### Failed Login Trend



Visualizes failed login activity over time.



\---



## Skills Demonstrated



\- Microsoft Sentinel

\- SIEM

\- SOAR

\- Kusto Query Language

\- Azure Monitor Agent

\- Log Analytics Workspace

\- Azure Logic Apps

\- Windows Event Logs

\- Security Monitoring

\- Threat Detection

\- Incident Response

\- Security Operations Center (SOC)

\- Cloud Security

\- Microsoft Azure



\---



\## Screenshots



The Screenshots folder contains images demonstrating:



\- Microsoft Sentinel Overview

\- Log Analytics Workspace

\- KQL Queries

\- Analytics Rule

\- Security Incident

\- Logic App Workflow

\- Email Notification



\---



\## Learning Outcomes



Through this project I gained practical experience with:



\- Building a cloud based SIEM environment

\- Collecting Windows Security Events

\- Writing Kusto Query Language (KQL)

\- Detecting authentication attacks

\- Creating Microsoft Sentinel Analytics Rules

\- Investigating Security Incidents

\- Automating incident response using Azure Logic Apps



\---



\## Future Improvements



Possible future enhancements include:



\- Microsoft Defender integration

\- Threat Intelligence integration

\- Additional Analytics Rules

\- Incident enrichment

\- Automated remediation workflows

\- Workbook dashboards

\- Custom hunting queries

# Results

## Failed Login Events

The following KQL query retrieves Windows failed logon events (Event ID 4625) collected by Microsoft Sentinel from the monitored virtual machine.

![Failed Login Events](images/failed-login-events.png)

The query results confirm that failed authentication attempts are successfully being ingested into the Log Analytics workspace.

---

## Failed Login Trend

A time-based visualization was created to identify spikes in failed authentication attempts and potential brute-force activity.

![Failed Login Trend](images/failed-login-trend.png)

---

## Incident Creation

A scheduled analytics rule was configured to detect multiple failed login attempts within a five-minute period. Once the rule conditions were met, Microsoft Sentinel automatically generated a security incident.

![Incident Creation](images/incident-list.png)

---

## Incident Investigation

The generated incident was investigated using the Microsoft Defender incident view, providing alert details and investigation context for the detected activity.

![Incident Investigation](images/incident-alert-details.png)

---

## SOAR Automation

A Microsoft Sentinel playbook was created using Azure Logic Apps. The playbook is triggered automatically when a Sentinel incident is created and executes an automated email notification workflow.

![SOAR Automation](images/logic-app-designer.png)

---

## Automated Email Notification

When the playbook executes successfully, an email notification is automatically sent containing information about the newly created Microsoft Sentinel incident.

![Automated Email Notification](images/email-notification.png)


\---



\## Author



\*\*Jaiveer Singh\*\*



Computer Science Student



University of Calgary



Information Security Concentration

