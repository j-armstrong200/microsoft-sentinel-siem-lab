# Microsoft Sentinel SIEM Investigation Lab

Microsoft Sentinel SIEM investigation lab using KQL to analyze simulated Microsoft Entra ID sign-in events and Azure Activity logs, investigate suspicious cloud activity, correlate security events, and document incident response recommendations.

## Project Overview

This project simulates a cloud security investigation using Microsoft Sentinel concepts and Kusto Query Language (KQL).

The investigation begins with suspicious authentication activity and follows the user's activity into the Azure environment. KQL queries are used to identify failed sign-ins, investigate a suspicious user, review Azure resource activity, and identify potentially high-risk cloud operations.

The goal is to demonstrate a basic SIEM investigation workflow from detection through investigation, correlation, risk assessment, and response recommendations.

## Investigation Scenario

Simulated authentication logs show:

- Multiple failed sign-in attempts for a user account
- Five failed attempts indicating possible brute-force activity
- A successful sign-in from an unusual geographic location
- Suspicious activity associated with the user's source IP

Azure Activity logs are then reviewed to determine what occurred after authentication.

The investigation identifies:

- Storage account key access
- Storage account modification
- Azure role assignment changes
- Activity associated with the investigated user and suspicious IP address

## KQL Queries

### Failed Sign-In Detection

`queries/failed_signins.kql`

Identifies unsuccessful authentication attempts and summarizes failed sign-ins by user.

### User Investigation

`queries/user_investigation.kql`

Investigates authentication activity associated with a specific suspicious user.

### Azure Activity Investigation

`queries/azure_activity_investigation.kql`

Creates a timeline of Azure resource activity performed by the investigated user.

### High-Risk Operations

`queries/high_risk_operations.kql`

Searches Azure Activity logs for potentially high-risk operations such as storage key access, storage account modifications, and Azure role assignment changes.

## Investigation Workflow

```text
Repeated failed sign-ins
          ↓
Successful unusual sign-in
          ↓
User and IP investigation
          ↓
Azure Activity review
          ↓
High-risk operation detection
          ↓
Event correlation
          ↓
Risk assessment
          ↓
Incident response recommendations
```

## Security Concepts Demonstrated

- Microsoft Sentinel
- SIEM investigation
- Kusto Query Language (KQL)
- Microsoft Entra ID sign-in monitoring
- Azure Activity Logs
- Authentication monitoring
- Brute-force detection
- Geographic login analysis
- Source IP investigation
- Security event correlation
- Cloud resource monitoring
- Privileged access monitoring
- Threat detection
- Incident investigation
- Risk assessment
- Incident response

## Project Files

- `signin_logs.csv` — simulated Microsoft Entra ID sign-in data
- `azure_activity.csv` — simulated Azure Activity data
- `queries/failed_signins.kql` — failed authentication detection
- `queries/user_investigation.kql` — suspicious user investigation
- `queries/azure_activity_investigation.kql` — Azure activity timeline
- `queries/high_risk_operations.kql` — potentially high-risk Azure operation detection
- `incident_report.md` — documented investigation findings and recommended response
- `README.md` — project documentation

## What I Learned

This project helped me understand how a SIEM can be used to investigate suspicious activity across multiple cloud data sources.

I practiced using KQL to filter, summarize, and investigate security events and learned how authentication events can be correlated with Azure resource activity to create an investigation timeline.

I also gained experience evaluating potentially high-risk cloud operations, documenting security findings, assessing risk, and recommending incident response actions.

## Disclaimer

This project uses fictional users, IP addresses, logs, and security events for educational and portfolio purposes. It does not connect to or contain data from a production Microsoft Azure environment.