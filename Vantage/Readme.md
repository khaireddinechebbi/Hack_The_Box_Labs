![alt text](image.png)
# This lab’s severity is very easy
# Description:
This investigation focuses on a security incident involving a small company that migrated part of its infrastructure to a private OpenStack cloud environment. A misconfiguration left a redirect to the cloud dashboard exposed on a public-facing web server.

Shortly after, the security team received an email claiming that sensitive user data had been exfiltrated by an attacker. Your objective is to analyze network traffic and system activity to reconstruct the attack chain.

Using a provided packet capture (PCAP), you will identify the attacker’s tools, reconnaissance methods, authentication attempts, API interactions with OpenStack services (Keystone and Swift), and eventual data exfiltration. The investigation also includes tracking persistence mechanisms established by the attacker through unauthorized user creation with administrative privileges.

By completing this lab, you will gain practical experience in:

* Web server fuzzing detection
* OpenStack architecture (Keystone & Swift services)
* PCAP analysis with Wireshark
* API endpoint discovery
* Cloud-based attack chain reconstruction
* MITRE ATT&CK mapping

This scenario simulates a real-world cloud compromise where misconfigurations and exposed services are leveraged to gain access, enumerate resources, and extract sensitive data.

# Scenario:
A small company moved some of its resources to a private cloud installation. The developers left the redirect to the dashboard on their web server. The security team got an email from the alleged attacker stating that the user data was leaked. It is up to you to investigate the situation.

## Task 1:
What tool did the attacker use to fuzz the web server ? (Format- include version e.g, nmap@7.80)
```text
ffuf@2.1.0
```

## Task 2:
Which subdomain did the attacker discover?
```text
cloud
```

## Task 3:
How many login attempts did the attacker make before successfully logging in to the dashboard?
```text
3
```

## Task 4:
When did the attacker download the OpenStack API remote access config file? (UTC)
```text
2025-07-01 09:40:29
```

## Task 5:
When did the attacker first interact with the API on controller node? (UTC)
```text
2025-07-01 09:41:44
```

## Task 6:
What is the project id of the default project accessed by the attacker?
```text
9fb84977ff7c4a0baf0d5dbb57e235c7
```

## Task 7:
Which OpenStack service provides authentication and authorization for the OpenStack API?
```text
keystone
```

## Task 8:
What is the endpoint URL of the swift service?
```text
http://134.209.71.220:8080/v1/AUTH_9fb84977ff7c4a0baf0d5dbb57e235c7
```

## Task 9:
How many containers were discovered by the attacker?
```text
3
```

## Task 10:
When did the attacker download the sensitive user data file? (UTC)
```text
2025-07-01 09:45:23
```

## Task 11:
How many user records are in the sensitive user data file?
```text
28
```

## Task 12:
For persistence, the attacker created a new user with admin privileges. What is the username of the new user?
```text
jellibean
```

## Task 13:
What is the password of the new user?
```text
P@$$word
```

## Task 14:
What is MITRE tactic id of the technique in task 12?
```text
T1136.003
```
