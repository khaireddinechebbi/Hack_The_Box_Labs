![alt text](image.png)

# This lab’s severity is Medium

# Scenario:
Our corp is suspected of being compromised, with initial analysis indicating that the workstation TriDsk-WKS02 may have served as the initial foothold for the attacker. The security team detected abnormal network activity originating from this endpoint, including outbound connections to suspicious external IP addresses.

# Note:
To make *.evtx files readable, use the paython script Evtx.py provided in this directory.
Usage: `python3 Evtx.py filename.evtx > filename.txt`

## Task 1:
Q: What is the name and version of the incident response agent installed on the endpoint?

* Note: Check Client_info.json

A: `Velociraptor 0.74.3`

## Task 2:
Q: At what time did the domain user account log into this workstation prior to the execution of the malicious data stealer infection?

* Note: Check logs, Event ID: 4624

A: `2025-10-08T15:07:43`

## Task 3:
Q: Identify the full URL of the malicious repository that was accessed and downloaded by the user, who mistakenly believed it to be a legitimate source.

* Note: Examen the browser's history of the user, path: TriDsk-WKS02-C.1dfcd21bd3d01cc0-F.D3JVHAK4B16NM/uploads/auto/C%3A/Users/yscott/AppData/Local/Microsoft/Edge/User Data/Default/

A: `https://github.com/saqua-ai/sequa-mcp`

## Task 4:
Q: Provide the CVE ID that allowed the downloaded repository to trigger the data-stealer automatically when opened in the target application.

* Note: Examen the code

A: `CVE-2025-54136`

## Task 5:
Q: Identify the full URL used to download the data-stealer.

* Note: check mcp.json

A: `https://up-date.hrzn.run//temp.exe`

## Task 6:
Q: Provide the first full URL observed that the data-stealer used to exfiltrate stolen data.

* Note: 

A: 

## Task 7:
Q: The data-stealer enumerates specific file extensions within a set of target directories. Identify the extensions the malware scanned (in the order the malware performed the searches) and provide the name for each.

* Note: examen the temp.exe strings

A: `.txt, .jpg, .png`

## Task 8:
Q: The data-stealer enumerates specific file extensions within a set of target directories. Identify the first four directories the malware scanned (in the order the malware performed the searches) and provide the name for each.

* Note: examen the temp.exe strings
* Hint: `SHGetKnownFolderPath`

A: `Documents, Desktop, Downloads, Pictures`

