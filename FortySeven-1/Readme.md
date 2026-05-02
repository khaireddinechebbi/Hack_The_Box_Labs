![alt text](image.png)
# This lab’s severity is very easy
# Description:
This investigation focuses on a threat actor identified as Mysterious Elephant, an Advanced Persistent Threat (APT) group targeting government and diplomatic entities through Hajj-themed phishing campaigns. By leveraging social engineering tactics aligned with regional and religious contexts, the group aims to compromise victims and exfiltrate sensitive data—particularly from WhatsApp.

Analysis of multiple intelligence sources, including security vendor reports and internal findings, reveals that the group’s activity dates back to 2022 and shares overlaps with other South Asian threat actors such as BITTER, suggesting possible collaboration or shared tooling.

Mysterious Elephant employs a range of custom-developed malware and loaders, including:

ORPCBackdoor, which uses Office Remote Procedure Call mechanisms and implements persistence via file checks (e.g., ts.dat).
Asyncshell-v2, an evolving backdoor whose command-and-control (C2) communication transitioned from TCP to HTTPS.
MemLoader HidenDesk, designed to evade sandbox detection by checking system conditions (e.g., minimum process count) and operating within a hidden desktop environment (MalwareTech_Hidden).

The group also utilizes specialized data exfiltration tools, such as:

Stom Exfiltrator, which recursively collects files from user directories like Desktop and Downloads.
ChromeStealer variants, targeting browser-stored data and credentials.

Their operations demonstrate strong reliance on script-based execution, particularly via PowerShell, and persistence techniques aligned with MITRE ATT&CK (e.g., T1547.001 – Registry Run Keys / Startup Folder). Data exfiltration is conducted over command-and-control channels (T1041), highlighting a structured and stealthy approach.

Notably, earlier campaigns leveraged tools like Vtyrei, previously linked to the Origami Elephant group, further reinforcing connections within the regional threat landscape. Additionally, exploitation of vulnerabilities such as CVE-2023-38831 in archive files indicates the group's ability to integrate known exploits into their delivery chain.

Overall, Mysterious Elephant demonstrates a well-organized and adaptive threat capability, combining social engineering, custom malware development, and evolving infrastructure to target high-value individuals and extract sensitive communications data.

# Scenario
An APT group is using Hajj-themed phishing lures to target and steal WhatsApp data from government and diplomatic officials. Our team has gathered fragmented intelligence from public cybersecurity vendor reports, blog posts, and internal security alerts. Your task is to build a comprehensive profile of the threat actor responsible. You must connect the dots between different reports to answer questions about their identity, tools, and motives.

## Task 1:
What is the primary name of the APT group described in the SecureList report?
```text
Mysterious Elephant
```

## Task 2:
According to the Knownsec 404 team's analysis(Evidence -3), since which year has this group's attack activity been dated back to?
```text
2022
```

## Task 3:
The group uses a custom backdoor that communicates via Office Remote Procedure Call (ORPCBackdoor). According to the Knownsec 404 team's analysis(Evidence -2), what is the name of the first malicious exported entry function?
```text
GetFileVersionInfoByHandleEx(void)
```
## Task 4:
The previously mentioned backdoor checks for a file before creating persistence. What is the name of the file?
```text
ts.dat
```

## Task 5:
The use of the backdoor links the APT to another well-known South Asian APT group. What is the name of this other group?
```text
BITTER
```

## Task 6:
The APT group we are currently investigating has consistently used and updated another backdoor since 2023, with its C2 communication evolving from TCP to HTTPS. What is the name of this tool?
```text
Asyncshell-v2
```

## Task 7:
To evade sandbox analysis, the MemLoader HidenDesk tool checks the number of active processes before running. What is the minimum number of processes required for it to proceed?
```text
40
```

## Task 8:
The MemLoader HidenDesk tool creates a covert environment for its activities by creating and switching to a specific environment. What is the name of this hidden desktop?
```text
MalwareTech_Hidden
```

## Task 9:
The MemLoader HidenDesk tool achieves persistence by placing a shortcut in the autostart folder to ensure it runs after a system reboot. What is the MITRE ATT&CK ID for the 'Registry Run Keys / Startup Folder' technique?
```text
T1547.001
```

## Task 10:
The actor uses several custom exfiltration tools targeting WhatsApp. What is the name of the tool that recursively searches specific directories, including the “Desktop” and “Downloads” folders?
```text
Stom Exfiltrator
```

## Task 11:
Kaspersky's analysis highlights the actor's heavy use of scripts for execution and deploying payloads. What is the MITRE ATT&CK ID for the 'PowerShell' technique?
```text
T1059.001
```

## Task 12:
In their early attack chains, Mysterious Elephant used a downloader that was previously associated with the Origami Elephant group. What was the name of this downloader?
```text
Vtyrei
```

## Task 13:
In a January 2024 campaign delivering an Asyncshell payload, which CVE was exploited in the malicious archive file?
```text
CVE-2023-38831
```

## Task 14:
What is the MD5 hash of the ChromeStealer Exfiltrator sample named WhatsAppOB.exe?
```text
9e50adb6107067ff0bab73307f5499b6
```

## Task 15:
The intelligence describes multiple custom tools designed to upload stolen data to the actor's servers. According to the MITRE ATT&CK framework, what is the ID for the 'Exfiltration Over C2 Channel' technique?
```text
T1041
```
