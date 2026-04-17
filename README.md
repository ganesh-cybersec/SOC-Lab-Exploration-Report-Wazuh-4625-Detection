## SOC Lab Exploration Report – Wazuh 4625 Detection
## Overview

This project focuses on Security Operations Center (SOC) analysis using Wazuh, with an emphasis on detecting and investigating Windows authentication failures, specifically Event ID 4625 (failed logon attempts).

The goal of this lab was to simulate real-world SOC workflows including log monitoring, alert analysis, and basic threat detection.

## Objectives
Understand how Wazuh collects and analyzes security logs
Detect failed login attempts (Event ID 4625)
Analyze brute-force attack patterns
Gain hands-on experience with SOC investigation workflows

## Lab Environment
SIEM Platform: Wazuh
Operating System: Windows (target machine)
Log Source: Windows Security Event Logs
Event Monitored:
Event ID 4625 – Failed logon attempt

## What is Event ID 4625?

Event ID 4625 is generated when a user fails to log into a Windows system. This can happen due to:

-Incorrect password
-Invalid username
-Account restrictions
-Brute-force attacks

Monitoring this event is critical for identifying unauthorized access attempts.

## Methodology
1. Log Collection

Wazuh agent was configured on the Windows machine to forward security logs to the Wazuh manager.

2. Rule Matching

Wazuh rules were used to detect:

Multiple failed login attempts
Suspicious login behavior

3. Alert Generation

When conditions were met, Wazuh generated alerts in the dashboard.

4. Analysis

Alerts were analyzed based on:

Source IP address
Target username
Frequency of attempts

## Findings

Multiple failed login attempts were detected within a short time window
Patterns indicated possible brute-force attack behavior
Repeated attempts targeting specific user accounts were observed

Sample Log (Event ID 4625)
Event ID: 4625
Account Name: x.x.x
Failure Reason: Unknown user name or bad password
Source IP: 192.168.x.x

Analysis

The repeated occurrence of Event ID 4625 suggests:

Potential brute-force or credential stuffing attack
Weak or commonly targeted usernames
Need for account lockout policies

## Mitigation Recommendations

Implement account lockout policies
Enforce strong password requirements
Enable multi-factor authentication (MFA)
Monitor and block suspicious IP addresses
Continuously monitor logs using Wazuh

## Key Learnings

Practical experience with SIEM tools
Understanding of Windows security events
Importance of log analysis in SOC operations
Detection of brute-force attack patterns

### Conclusion

This lab demonstrated how Wazuh can be used effectively in a SOC environment to detect and analyze failed authentication attempts. Monitoring Event ID 4625 provides valuable insight into potential security threats and helps strengthen system defenses.
