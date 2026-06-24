# Azure Honeypot SOC Investigation: Analysis of 1,874 Failed Authentication Attempts Using Splunk SIEM

## Project Overview

This project documents the deployment of an internet-exposed Azure Windows Virtual Machine (VM) configured as a honeypot and monitored using Splunk SIEM for security event collection and analysis.

The objective of this project was to observe real-world attack activity targeting a publicly accessible cloud asset, investigate authentication-related events, identify attacker behavior, and map observed techniques to the MITRE ATT&CK framework.

During a 24-hour observation period, the honeypot recorded **1,874 failed authentication attempts** originating from multiple countries, including Hong Kong, India, the Netherlands, and the Philippines. Analysis of Windows Security Event Logs revealed evidence of automated brute-force attacks, username enumeration attempts, and repeated targeting of privileged accounts.

Investigation of attacker activity showed distinct behavioral patterns. One source generated 1,493 failed login attempts against the **Administrator** account, indicating a high-volume brute-force attack. Another source attempted authentication against numerous common usernames such as **ADMIN, ROOT, SERVER, STUDENT, SUPPORT, and TEST**, suggesting username enumeration and credential-guessing activity.

The collected telemetry was analyzed using Splunk Enterprise, correlated with Windows Security Event IDs, enriched with geolocation data, and mapped to relevant MITRE ATT&CK techniques including:

* T1110 – Brute Force
* T1021 – Remote Services
* T1078 – Valid Accounts

This project demonstrates cloud security monitoring, SIEM investigation workflows, threat analysis, and incident documentation techniques commonly used by Security Operations Center (SOC) analysts.

## Key Findings

* Total Failed Login Attempts: 1,874
* Observation Window: 24 Hours
* Countries Observed: 4
* Unique Attacker IPs: 5
* Highest Activity Source: Hong Kong (1,493 failed logins)
* Most Targeted Account: Administrator
* Primary Technique Observed: Brute Force (MITRE ATT&CK T1110)
