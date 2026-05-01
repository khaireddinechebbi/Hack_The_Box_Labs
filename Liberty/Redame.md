![alt text](image.png)

# This lab’s severity is Medium

# Scenario:
Liberty launched a massive project with a budget exceeding $100 million, with the goal of granting true freedom to humanity.

One day, a system administrator discovered a shared folder configured with “Full Control” permissions granted to “Everyone”, raising concerns about a potential security incident.

You have been tasked with investigating evidence collected from the affected endpoint to determine what occurred. Threat Intelligence has previously identified that an employee’s credentials were harvested by a RedLine Stealer, which is suspected to have been used for initial access to this system.

## Task 1:
Q: You suspect that a threat actor might conduct password spraying attack on this server, How many failed logon attempts identified before successfully identifying the correct pair of the credential?

* Note: check how many failed logons in short time Event ID: 4625

A: `6`

## Task 2:
Q: What is the user that was identified by the threat actor?

* Note: check the successfull logon after the failed logons.

A: `v.hunter`

## Task 3:
Q: There is a shared folder that can be accessed by all users, what is the name of this shared folder?

* Note: SMB protocol is used in Windows to connect shared resources like files and folders, check smb security logs.

A: `Proposal`

## Task 4:
Q: The threat actor uploaded several files to the previously identified shared folder. One of these files can be used to capture the hash of a user who opens it. What is the name of that file?

* Note: Find it in the content of $MFT file

A: `Proposal.url`

## Task 5:
Q: What is the full URL used by threat actor to mimic the fake proposal of the project?

* Note: Find it in the content of $MFT file

A: `http://argonaut.ark/proposal.html`

## Task 6:
Q: What is the full UNC path of the network share that the threat actor used to capture hash of the victim?

* Note: Find it in the content of $MFT file

A: `\\192.168.189.129\%USERNAME%.icon`

## Task 7:
Q: What is the format of the hash that the threat actor captured via this method?

* Note: Check security.evtx

A: `Net-NTLMv2`

## Task 8:
Q: What is the full name of the second compromised user?

* Note: check SAM file

A: `Kuneo Texus`

## Task 9:
Q: When was the time that the threat actor connected to the server via RDP in UTC?

* Note: Check security.evtx, event ID: 4624, session type: 10

A: `2025-06-11 14:44:48`

## Task 10:
Q: The threat actor discovered a folder that stores files about the project, What is the full path of this folder?

* Note: Find it in the content of $MFT file

A: `C:\ProjectArk`

## Task 11:
Q: The threat actor created an archive file containing all files of the previously identified folder, What is the name of this archive file?

A: `arkproj.zip`

## Task 12:
Q: What is the total bytes of all files on that folder which were compressed into previously identified archive file? (not including Zone Identifier)

* Note: sum the size of all files in the folder

A: `783907`

## Task 13:
Q: The threat actor uploaded the previously identified file to C2 website, What is the domain of this website?

A: `yourc2filemanager.cn`

## Task 14:
Q: While reviewing users on this server, you found a suspicious user on this server, What is the name of this user?

* Note: Check the SAM and SYSTEM files

A: `t.minami`

## Task 15:
Q: The threat actor installed a web-based gateway as a backdoor to the server. What is the full command used to install this feature?

* Note: ./Users/k.texus/AppData/Roaming/Microsoft/Windows/PowerShell/PSReadline/ConsoleHost_history.txt

A: `Install-WindowsFeature -Name WindowsPowerShellWebAccess -IncludeManagementTools`

## Task 16:
Q: Which protocol has to be enabled to use this feature?

A: `WinRM`

## Task 17:
Q: Provide the UTC timestamp when the threat actor confirmed successful backdoor access through the previously identified user account.

A: `2025-06-11 14:54:55`

## Tssk 18:
Q: What is the Session ID of this connection?

A: `LIBERYSV08\t.minami.250611.075455`

## Task 19:
Q: Provide the UTC timestamp When was this session terminated by the threat actor

A: `2025-06-11 14:55:40`

## Task 20:
Q: What is the name of shared folder that was created by the threat actor during the invasion?

* Note: check HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Shares

A: `ProjectArk`
