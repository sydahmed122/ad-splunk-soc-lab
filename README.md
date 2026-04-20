<h1 align="center">SOC Lab: Active Directory Monitoring with Splunk</h1>

<p align="center">
A hands-on SOC project simulating real-world log monitoring, attack detection, and incident analysis using Splunk SIEM.
</p>

<hr>

<h2>Objective</h2>
<p>
The objective of this project is to build a real-world SOC lab where logs from an Active Directory environment are centrally collected, monitored, and analyzed using Splunk SIEM to detect suspicious activities such as brute-force attacks and failed login attempts.
</p>

<hr>

<h2>Project Overview</h2>
<p>
This project simulates an enterprise SOC environment with Active Directory, a Windows 10 client, and Splunk SIEM. Logs are collected using Sysmon and Splunk Universal Forwarder, and attack scenarios are generated using Kali Linux and Atomic Red Team to test detection capabilities.
</p>

<hr>

<h2>Lab Architecture</h2>
<p><i>(Add your architecture image below)</i></p>

<img src="screenshots/architecture.png" width="700">

<hr>

<h2>Tools & Technologies</h2>
<ul>
  <li>Splunk SIEM</li>
  <li>Active Directory (Windows Server)</li>
  <li>Windows 10</li>
  <li>Kali Linux</li>
  <li>Sysmon</li>
  <li>Splunk Universal Forwarder</li>
  <li>Atomic Red Team</li>
</ul>

<hr>

<h2>Step-by-Step Implementation</h2>

<h3>1. Environment Setup</h3>
<ul>
  <li>Created virtual lab network</li>
  <li>Connected all systems within the same subnet</li>
</ul>

<h3>2. Active Directory Setup</h3>
<ul>
  <li>Installed Windows Server</li>
  <li>Configured Domain Controller (corp.local)</li>
  <li>Created users</li>
</ul>

<h3>3. Splunk Setup</h3>
<ul>
  <li>Installed Splunk Enterprise</li>
  <li>Configured indexes and data inputs</li>
</ul>

<h3>4. Log Forwarding</h3>
<ul>
  <li>Installed Sysmon on endpoints</li>
  <li>Installed Splunk Universal Forwarder</li>
  <li>Forwarded logs to Splunk</li>
</ul>

<h3>5. Log Verification</h3>
<ul>
  <li>Verified Windows Event Logs</li>
  <li>Verified Sysmon logs in Splunk</li>
</ul>

<h3>6. Attack Simulation</h3>
<ul>
  <li>Used Kali Linux</li>
  <li>Used Atomic Red Team</li>
  <li>Simulated brute-force attacks</li>
</ul>

<hr>

<h2>Detection Use Case: Brute Force Attack</h2>

<h3>Goal</h3>
<p>Detect multiple failed login attempts indicating brute-force behavior.</p>

<h3>Logs Used</h3>
<ul>
  <li>Windows Security Logs</li>
  <li>Event ID 4625 (Failed Login)</li>
</ul>

<h3>Detection Logic</h3>
<ul>
  <li>Multiple failed logins</li>
  <li>Same user or IP</li>
  <li>Short time duration</li>
</ul>

<h3>Splunk Query</h3>
<pre>
index=windows EventCode=4625
| stats count by user, src_ip
| where count > 5
</pre>

<h3>Findings</h3>
<ul>
  <li>Detected repeated failed login attempts</li>
  <li>Identified brute-force activity</li>
</ul>

<h3>Response (SOC Perspective)</h3>
<ul>
  <li>Investigated source IP</li>
  <li>Recommended blocking attacker</li>
  <li>Escalated incident</li>
</ul>

<hr>

<h2>Screenshots</h2>

<p><b>Splunk Logs:</b></p>
<img src="screenshots/logs.png" width="700">

<p><b>Detection Results:</b></p>
<img src="screenshots/detection.png" width="700">

<hr>

<h2>Key Learnings</h2>
<ul>
  <li>SIEM log analysis</li>
  <li>Windows Event monitoring</li>
  <li>Threat detection techniques</li>
  <li>SOC workflow understanding</li>
</ul>

<hr>

<h2>Future Improvements</h2>
<ul>
  <li>Integrate Shuffle (SOAR)</li>
  <li>Add more detection rules</li>
  <li>Enable alert automation</li>
</ul>

<hr>

<h2>Author</h2>
<p>
Syed Mujtaba Ahmed<br>
Aspiring SOC Analyst
</p>
