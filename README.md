# Active-Directory-Monitoring-with-Splunk
Built a SOC lab integrating Active Directory with Splunk SIEM to monitor and analyze security logs. Configured log forwarding using Sysmon and Splunk Universal Forwarder, and simulated attacks (brute-force, failed logins) using Kali Linux and Atomic Red Team. Detected suspicious activity using Splunk queries and event logs.

 SOC Lab: Active Directory Monitoring with Splunk
## Objective

The objective of this project is to design and implement a real-world SOC (Security Operations Center) lab where logs from an Active Directory environment are centrally collected, monitored, and analyzed using Splunk SIEM to detect and investigate suspicious activities such as brute-force attacks and failed login attempts.

## Project Overview

In this project, I built a complete SOC lab environment simulating an enterprise network. The setup includes a Windows Server configured as an Active Directory Domain Controller, a Windows 10 client machine, and a Splunk server for centralized log collection and analysis.

To generate real attack data, I simulated adversary behavior using Kali Linux and Atomic Red Team. The generated logs were ingested into Splunk and analyzed using detection queries to identify malicious activity.

## Lab Architecture

(Add your architecture image here)
## Network Details:

Domain: corp.local
Network Range: 192.168.x.x
Component	Role
Active Directory (Windows Server)	Domain Controller
Windows 10	Client Machine
Splunk Server	SIEM
Kali Linux	Attacker Machine
 Tools & Technologies Used
Splunk SIEM
Active Directory (Windows Server)
Windows 10
Kali Linux
Sysmon (for enhanced logging)
Splunk Universal Forwarder
Atomic Red Team
## Step-by-Step Implementation
🔹 1. Environment Setup
Created a virtual lab network
Connected all machines within the same subnet
Assigned IP addresses
🔹 2. Active Directory Configuration
Installed Windows Server
Promoted it to Domain Controller
Configured domain: corp.local
Created users and configured basic policies
🔹 3. Splunk SIEM Setup
Installed Splunk Enterprise
Configured data inputs
Set up indexes for log ingestion
Verified Splunk web interface
🔹 4. Log Collection & Forwarding
On Active Directory & Windows 10:
Installed Sysmon to generate detailed logs
Installed Splunk Universal Forwarder
Configured log forwarding to Splunk server
🔹 5. Log Verification in Splunk
Verified ingestion of:
Windows Event Logs
Sysmon logs
Ensured logs were searchable in Splunk
🔹 6. Attack Simulation

## To simulate real-world threats:

Used Kali Linux for attack execution
Used Atomic Red Team for structured attack scenarios

## Simulated Attacks:

Brute-force login attempts
Multiple failed authentication attempts
 Detection Use Case: Brute Force Attack
 Objective

Detect multiple failed login attempts indicating a brute-force attack.

 Logs Analyzed
Windows Security Event Logs
Event ID 4625 (Failed Logon)
 Detection Logic
Multiple failed login attempts
Same user or source IP
Within a short time window
 Splunk Query
index=windows EventCode=4625
| stats count by user, src_ip
| where count > 5
## Findings
Identified repeated failed login attempts
Detected potential brute-force behavior
Correlated events using Splunk
 SOC Response (Simulated)
Investigated source IP
Identified suspicious login patterns
Recommended blocking malicious IP
Escalation to higher-level analysts
## Screenshots

(Add screenshots here)

Splunk dashboard
Event logs (4625)
Query results
Sysmon logs

## Example:

![Splunk Logs](screenshots/logs.png)
 Key Learnings
Understanding how SIEM collects and analyzes logs
Working with Windows Event Logs and Sysmon
Detecting authentication-based attacks
Hands-on experience with SOC workflows
Importance of log correlation and monitoring
 Future Improvements
Integrate Shuffle (SOAR) for automation
Connect with TheHive for case management
Create additional detection rules
Implement real-time alerting
## Author

Syed Mujtaba Ahmed
 SOC Analyst
