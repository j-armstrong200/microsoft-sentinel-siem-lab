# Microsoft Sentinel SIEM Investigation Report

## Incident Summary

A simulated security investigation identified repeated failed authentication attempts followed by a successful sign-in from an unusual geographic location. Additional Azure activity associated with the user and source IP was reviewed to determine whether suspicious cloud activity occurred after authentication.

## User Investigated

- User: awilson@contoso.com
- Initial Activity: Multiple failed sign-in attempts
- Suspicious Location: Russia
- Severity: High

## Investigation

Microsoft Sentinel-style KQL queries were used to analyze simulated Microsoft Entra sign-in and Azure Activity logs.

The investigation identified:

- Five failed sign-in attempts associated with the user account
- A subsequent successful sign-in from an unusual geographic location
- Azure activity associated with the suspicious source IP
- Access to Azure storage account keys
- Modification of an Azure storage account
- An Azure role assignment change

## Event Correlation

Authentication and Azure Activity events were correlated using the user account, source IP address, and timestamps.

The correlated activity demonstrated how multiple security events can be combined to build an investigation timeline and identify potentially suspicious behavior that may not be apparent from a single event.

## Risk Assessment

The combination of repeated authentication failures, an unusual successful sign-in, storage account key access, resource modification, and a role assignment change would warrant further investigation in a production environment.

These events could indicate unauthorized access or account compromise, but additional evidence would be required before reaching that conclusion.

## Recommended Response

- Validate the sign-in activity with the user
- Review authentication and session details
- Review MFA and Conditional Access information
- Investigate the source IP and device
- Review changes made to Azure resources
- Review Azure role assignments and privileged access
- Revoke suspicious sessions if appropriate
- Reset credentials if compromise is confirmed
- Escalate through the incident response process as required

## Conclusion

This lab demonstrates a basic Microsoft Sentinel SIEM investigation workflow using KQL, simulated Microsoft Entra sign-in logs, and Azure Activity logs. The investigation correlates authentication and cloud resource activity to identify suspicious behavior and document recommended incident response actions.

## Disclaimer

All users, IP addresses, logs, and security events used in this project are fictional and are provided solely for educational and portfolio purposes.