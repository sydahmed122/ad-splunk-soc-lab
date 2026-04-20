# SOC Lab: Active Directory + Splunk SIEM Detection Environment

![GitHub repo size](https://img.shields.io/github/repo-size/your-username/your-repo-name)
![GitHub last commit](https://img.shields.io/github/last-commit/your-username/your-repo-name)
![License](https://img.shields.io/github/license/your-username/your-repo-name)

## Overview

This project demonstrates the design and implementation of a real-world **Security Operations Center (SOC) lab environment** using **Active Directory** and **Splunk SIEM**. The lab simulates an enterprise network where logs from domain-joined systems are centrally collected, monitored, and analyzed to detect suspicious activity. A clear README is valuable because it tells readers what the project does, how to use it, and why it matters [page:1][page:2].

The environment includes a Windows Server configured as an **Active Directory Domain Controller**, a **Windows 10 client**, a **Splunk server** for log aggregation and analysis, and a **Kali Linux attacker machine**. Sysmon and Splunk Universal Forwarders are deployed to provide detailed telemetry and real-time log forwarding.

## Architecture

The lab topology includes:
- **Domain:** `corp.local`
- **Network:** `192.168.1.0/24`
- **Splunk Server:** `192.168.10.10`
- **Active Directory Server:** `192.168.10.7`
- **Attacker Machine:** `192.168.10.250`

The diagram below shows the setup you built.

[image:1]

## Features

- Centralized log collection using **Splunk Universal Forwarder**.
- Endpoint telemetry collection using **Sysmon**.
- Windows authentication event monitoring with focus on **Event ID 4625**.
- Detection of failed login attempts and possible brute-force activity.
- Simulation of adversary behavior using **Kali Linux** and **Atomic Red Team**.
- SOC-style investigation workflow for alerting and log analysis.

## Tools Used

- **Windows Server**
- **Windows 10**
- **Active Directory**
- **Splunk Enterprise**
- **Sysmon**
- **Splunk Universal Forwarder**
- **Kali Linux**
- **Atomic Red Team**

## Detection Scenarios

The project generated and analyzed security events such as:
- Failed login attempts.
- Suspicious authentication behavior.
- Brute-force-style login activity.
- Endpoint process telemetry through Sysmon.
- Forwarded logs for correlation and investigation in Splunk.

## Skills Demonstrated

This project shows practical experience in:
- SOC lab design.
- SIEM configuration.
- Windows event log analysis.
- Threat detection and investigation.
- Log forwarding and telemetry collection.
- Basic adversary simulation in a controlled environment.

## How It Works

1. Windows systems are joined to the domain.
2. Sysmon collects detailed endpoint activity.
3. Splunk Universal Forwarder sends logs to the Splunk server.
4. Authentication and process events are indexed in Splunk.
5. Detection logic identifies suspicious behavior.
6. Analysts can investigate and validate alerts using Splunk queries.

## Example Splunk Query

```spl
index=windows sourcetype=WinEventLog:Security EventCode=4625
| stats count by Account_Name, Workstation_Name, Failure_Reason
| sort -count
```

## Future Improvements

Planned enhancements for this lab include:
- Integrating **Shuffle** for SOAR-based automation.
- Expanding detection rules and alert coverage.
- Adding more attack scenarios for validation.
- Building incident response playbooks.
- Improving dashboards for SOC monitoring.

## Project Value

This lab reflects how a security analyst monitors authentication activity, identifies anomalies, and responds to threats in a controlled enterprise-like environment. It also demonstrates hands-on knowledge of SIEM workflows, endpoint visibility, and detection engineering.

## Contact

Created by **Your Name**  
GitHub: `your-username`  
LinkedIn: `your-linkedin-profile`

## License

This project is licensed under the **MIT License**.
