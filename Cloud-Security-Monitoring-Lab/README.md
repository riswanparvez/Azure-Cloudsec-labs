
🛡️ Azure Sentinel Brute Force Detection using SIEM

🚀 Key Achievement

Detected simulated brute force login attempts using Microsoft Sentinel
Built a custom KQL detection rule to identify repeated failed login attempts
Generated automated security incidents using Sentinel analytics rules

📌 Overview

This project demonstrates how to deploy and configure Microsoft Sentinel (SIEM) in Azure to detect brute force login attempts against a Windows virtual machine.

A Windows Server VM was deployed in Azure and configured to send Windows Security Event Logs to a Log Analytics Workspace using the Azure Monitor Agent (AMA).

These logs were then analyzed using Kusto Query Language (KQL) to detect abnormal authentication behavior. When the detection threshold was exceeded, Microsoft Sentinel automatically generated a security incident.

This lab simulates how a Security Operations Center (SOC) detects and investigates credential-based attacks.

🎯 Objective

Simulate and detect a brute force login attack using Microsoft Sentinel by:

Collecting Windows authentication logs
Analyzing logs using KQL queries
Creating a custom Sentinel detection rule
Generating a security incident when attack patterns are detected
🏗️ Architecture

Azure VM → Windows Security Logs → Azure Monitor Agent → Log Analytics Workspace → Microsoft Sentinel → Detection Rule → Security Incident

⚙️ Steps Implemented
1. Deployed Azure Infrastructure

Created the required Azure resources:

Resource Group
Virtual Network (VNet)
Network Security Group (NSG)
Public IP
Windows Server 2022 Virtual Machine

Purpose:
Create a target environment to simulate login attacks and collect authentication logs.

2. Created Log Analytics Workspace

A Log Analytics Workspace was deployed to act as the centralized logging platform.

Purpose:

Store security logs
Query logs using KQL
Integrate with Microsoft Sentinel for threat detection
3. Enabled Microsoft Sentinel

Microsoft Sentinel was deployed on the Log Analytics Workspace.

Purpose:

Provide SIEM functionality
Enable threat detection and monitoring
Generate security incidents based on detection rules
4. Configured Log Collection using Azure Monitor Agent (AMA)

The Azure Monitor Agent (AMA) was installed on the Windows VM.

A Data Collection Rule (DCR) was configured to collect:

Windows Security Event Logs

Important authentication events collected:

Event ID	Description
4624	Successful login
4625	Failed login attempt

Purpose:

Collect authentication telemetry to detect suspicious login behavior.

5. Verified Log Ingestion

Used a KQL query to verify that failed login events were successfully collected.

SecurityEvent
| where EventID == 4625

Purpose:

Confirm that Windows authentication logs were successfully ingested into Sentinel.

6. Created Brute Force Detection Query

A KQL query was created to detect repeated failed login attempts within a short time window.

SecurityEvent
| where EventID == 4625
| summarize FailedAttempts = count() by Account, Computer, bin(TimeGenerated, 5m)
| where FailedAttempts >= 5

Purpose:

Identify potential brute force attacks by detecting 5 or more failed login attempts within 5 minutes.

7. Simulated Brute Force Login Attempts

Multiple incorrect RDP login attempts were performed against the Windows VM.

This generated multiple Event ID 4625 (failed login) entries.

Purpose:

Simulate a real-world credential attack scenario.

8. Created Sentinel Analytics Rule

A custom Sentinel Analytics Rule was created using the KQL detection query.

Rule configuration:

Rule Name: Possible Brute Force Attack
Query Frequency: Every 5 minutes
Lookup Period: Last 5 minutes
Threshold: ≥ 5 failed login attempts
Severity: Medium

Purpose:

Automatically detect brute force attacks and generate security alerts.

9. Generated Security Incident

When the detection rule triggered, Microsoft Sentinel generated a security incident.

Incident details:

Field	Value
Incident Name	Possible Brute Force Attack
Severity	Medium
Category	Credential Access
Detection Source	Microsoft Sentinel

Purpose:

Demonstrate real-time threat detection and incident generation within a SIEM platform.

⚠️ Challenges Faced

Understanding Microsoft Sentinel navigation and configuration
Azure Monitor Agent configuration delays
Analytics rule detection timing and query thresholds
Initial confusion around Azure Activity logs vs Windows Security logs

🧠 Key Learnings

How SIEM platforms ingest and analyze security logs
Using Kusto Query Language (KQL) to detect suspicious activity
Understanding Windows authentication events (4624 vs 4625)
How brute force attacks are detected in SOC environments
How analytics rules convert log patterns into security incidents

🎯 Outcome

Successfully detected simulated brute force login attempts
Created a custom detection rule using KQL
Generated automated security incidents using Microsoft Sentinel
Built a working SIEM detection pipeline in Azure

📚 Skills Demonstrated

Cloud Security Monitoring
SIEM Deployment and Configuration
Microsoft Sentinel
Log Analytics Workspace
Azure Monitor Agent (AMA)
KQL Query Writing
Threat Detection Engineering
SOC Incident Detection

