# TryHackMe Cybersecurity 101 Journal

This is my ongoing journal documenting cybersecurity training from TryHackMe, Active Directory coursework, and hands-on labs.

---

## 🛠️ Current Focus: Active Directory & Network Analysis

- Tools used: Wireshark, Event Viewer, PowerShell, Netcat
- Topics covered: Domain enumeration, user/group permissions, Kerberoasting basics, and common AD misconfigurations
- Platforms: TryHackMe Cybersecurity 101, college lab environments

---

## ✅ Completed Modules & Topics

- Networking Fundamentals (TryHackMe & School)
- Cyber Hygiene
- Linux Basics
- Intro to SIEM & Incident Response
- Virtualization & Server Configuration
- Computer Forensics (college lab work)

---

## 🔧 Tools Explored

- Wireshark (live capture & analysis)
- Windows Event Viewer
- Netcat
- Bash & PowerShell (basics)

## ✅ Current Progress: Cybersecurity 101 Path (In Progress)


# 🛡️ Cybersecurity 101 Progress – Alfredo San Miguel

Welcome to my cybersecurity lab journal, documenting my progress through TryHackMe's Cybersecurity 101 pathway. This page outlines the skills and labs I’ve completed so far as I build foundational knowledge in cybersecurity operations, system administration, and threat analysis.

---

## ✅ Current Progress: Cybersecurity 101 Path (In Progress)

### 🧠 Introduction to Cybersecurity
- Learned about threat actors, the CIA triad, and basic attack vectors
- Explored malware types and common vulnerabilities

### 🌐 Networking Fundamentals
- Studied the OSI model and TCP/IP layers
- Practiced identifying common ports and services (e.g., SSH, HTTP, DNS)
- Used **Wireshark** to analyze real packet captures and detect traffic patterns

### 🐧 Linux Fundamentals
- Navigated the Linux terminal (Red Hat–based systems)
- Practiced creating/modifying files, managing directories, using `chmod`/`chown`
- Explored user and group permissions

### 🪟 Windows Fundamentals
- Investigated Windows services, Task Manager, and regedit
- Analyzed processes and file structures used in real-world systems

### 🏢 Active Directory Basics
- Gained understanding of domain structure, authentication, and group policy
- Explored enumeration tools for discovering AD objects

---

### 🏢 Active Directory (Completed)
- Explored the structure and role of Active Directory within Windows-based networks
- Learned how authentication, domain controllers, users, and groups operate within AD
- Practiced enumerating AD information using tools like `rpcclient`, `enum4linux`, and `nmap`
- Simulated real-world attacker enumeration techniques against misconfigured AD environments
- Gained understanding of concepts like Kerberos, LDAP, and Group Policy Objects (GPO)

🛠 Tools used:
- `rpcclient`
- `enum4linux`
- `nmap`
- AD-based virtual lab environment (TryHackMe)

🎯 Skills Gained:
- Domain enumeration and reconnaissance
- Identifying vulnerable user accounts and misconfigured shares
- Understanding authentication protocols and privilege escalation paths within AD



💻 Windows Command Line (Completed)

Platform: TryHackMe — Cybersecurity 101 Path
Difficulty: Easy
Focus: Navigating Windows via CMD, process management, file operations, and basic networking commands.

Key Skills & Commands Learned:

Navigation & File Management:

cd, cd .., cd \ for directory traversal

dir & dir /a to list visible and hidden files

type and more to read file contents

Using wildcards (*.txt) for batch operations

Process Management:

tasklist /FI "imagename eq <process>" to filter running processes

taskkill /PID <pid> to terminate processes by PID

System Information:

ver and systeminfo to retrieve OS details

Identified OS version from SSH banner: Windows Server 2022 (10.0.20348.2655)

Networking Commands:

ipconfig / ipconfig /all for IP configuration

ping, tracert, nslookup for connectivity & DNS resolution

netstat for viewing established connections and listening ports

System Control:

shutdown /s to shut down

shutdown /r to restart

shutdown /a to abort a scheduled shutdown

Notable Task:

SSH into target Windows VM via AttackBox, navigate hidden directory C:\Treasure\Hunt, locate and read flag.txt to retrieve flag THM{CLI_POWER}.

Reflection:
This module strengthened my confidence in navigating and managing Windows systems without relying on the GUI. Skills learned here directly translate to real-world scenarios like incident response, malware removal, and system auditing in a command-line–only environment.



 Enterprise Threat Hunting & Defensive Operations: Multi-Vector Attack Analysis📌 Project OverviewThis repository documents a series of hands-on, multi-stage cyber defense labs demonstrating advanced network auditing, threat hunting, and incident response methodologies. The project covers simulated adversary actions ranging from network and application-layer Denial of Service (DoS) attacks to internal network sniffing via ARP spoofing and lateral movement path analysis within a switched enterprise infrastructure.
 
 🚀 Lab 1: Multi-Stage DoS Evaluation & Impact AssessmentObjective: Analyze system resource depletion patterns by executing and monitoring Layer 3/4 network floods alongside Layer 7 application crashes within a two-person tactical defense cell.
  Tools Used: hping3, Low Orbit Ion Cannon (LOIC), Wireshark, Windows Task Manager, Linux System Monitor.📊 Tactical Framework & ComparisonThe impact parameters of infrastructure-level flooding were mapped against application-level exploitation vectors:Attack VectorLayer (OSI)Primary MechanismPrimary Host Resource ImpactDetection/Mitigation FootprintSYN FloodLayer 4 (TCP)Exhausts connection queue with incomplete "half-open" state handshakes.Network/Ethernet (Bandwidth pipe saturation).High anomaly visibility via clear Wireshark filters (tcp.flags.syn == 1).ICMP FloodLayer 3 (IP)Saturates hardware line rates with heavy ping echo requests (hping3 -1).Network Bandwidth.High volume threshold alert triggers.HTTP FloodLayer 7 (App)Flood of valid syntactic HTTP requests via LOIC over threading architectures.CPU (100% Core Spike) & RAM exhaustion.Low visibility; masquerades as legitimate user web traffic.bash# Executing an aggressive Layer 4 SYN flood to saturate host connection queues
sudo hping3 -S -p 80 --flood 172.26.31.210

# Executing a Layer 3 ICMP bandwidth exhaustion flood
sudo hping3 -1 -c 100 172.26.31.210
Use code with caution.💡 Core Defensive InsightWhile Layer 3/4 floods target physical network pipeline capacity, Layer 7 application-layer attacks are far more effective at forcing complete host unresponsiveness. They force the operating system's compute engine to consume massive CPU cycles rendering complex application payloads, while safely blending into standard HTTP/S streams to bypass rudimentary firewalls.

🔎 Lab 2: C2 Beaconing Detection via Active ARP SpoofingObjective: Conduct localized traffic interception inside a switched network environment to capture and log hardcoded malware "heartbeats" communicating with a remote server.Tools Used: nmap, Ettercap (Unified Sniffing & ARP Poisoning Engine), Wireshark, PowerShell.mermaidgraph LR
    Victim[Win11 VM: 172.26.31.173] <--> Attacker[Parrot OS: 172.26.31.6]
    IR_Kali[Kali Threat Hunter] -.-> |ARP Poisoning| Victim
    IR_Kali -.-> |ARP Poisoning| Attacker
Use code with caution.🛠️ Execution PipelineNetwork Discovery: Mapped active nodes on the 172.26.31.0/24 subnet using Nmap ping sweeping (nmap -sn) to isolate target Module4-Win11-vm12.Man-in-the-Middle (MitM) Positioning: Injected gratuitous ARP replies into the local cache tables via Ettercap, mapping the Attacker IP (172.26.31.6) and Victim IP (172.26.31.173) through the threat hunter's network interface card.Traffic Extraction: Applied Wireshark filtering (tcp.port == 4444) to parse the intercepted streams, identifying a rhythmic Command and Control (C2) callback loop.Host-Level Verification: Audited local session states inside the host environment using forensic logging configurations (activity.log), validating a persistent automated beacon outbound execution cadence operating precisely on a 10-second interval cycle.

📊 Lab 3: Attack Surface Auditing & Lateral Movement AnalysisObjective: Map structural attack vectors from an exposed external DMZ gateway to high-value internal directory architecture targets.Tools Used: nmap (Service Versioning & OS Fingerprinting), smbclient.
🔍 Dual-Host Profile BaselinesAn offensive path audit was mapped across two active infrastructure targets:1. Target A: The Perimeter Gateway (172.26.31.231 - Hostname: bwapp)Infrastructure Vendor: Proxmox Server Solutions GmbH virtual interface.Authorized Baselines: Apache httpd 2.2.8 running over standard ports 80/tcp and 443/tcp.Unauthorized Risk Profile: An unmapped, shadow instance of nginx 1.4.0 actively bound to alternative administration ports 8080/tcp and 8443/tcp.2. Target B: The Crown Jewel (172.26.31.200 - Hostname: WINSVR25)Primary Exploitation Vector: Exposed Terminal Services/RDP bound to 3389/tcp.Secondary Infrastructure Vector: Active Windows RPC mapping service operating on 135/tcp.Share Enumeration Audit: System share paths queried via smbclient -L //172.26.31.200 -N. High-level structural definitions (ADMIN$, C$, IPC$) were identified. Null session restrictions successfully forced migration to modern SMB2/3 configuration rulesets.📈 Structural Lateral Attack Chain Mapping[Perimeter Web Exploit: Port 80] 
       │
       ▼
[Linux Root Compromise (BEE-BOX)] 
       │
       ▼
[Credential Extraction / Memory Dump] 
       │
       ▼
[SMB/RDP Administrative Pivot: Ports 445/3389] 
       │
       ▼
[Windows Domain Controller Compromise (WINSVR25)]
🌟 Enterprise Asset Triage LogicWhen combining live service scan telemetry with an official corporate Asset Inventory Matrix, anomalous data points can decisively differentiate between infrastructure anomalies: Identifying a Rogue Device: Occurs when hardware attributes (such as a Proxmox MAC address prefix) appear inside an environment strictly baselined for vendor hardware (e.g., an all-HP deployment), or when a device uses naming conventions completely out of line with corporate naming baselines. Identifying a Compromised Device: Occurs when a validated device matching corporate asset logs displays stark operational variations from its known baseline—such as a standard web host suddenly listening on 22 different ports, running unauthorized services like nginx 1.4.0 or open bind shells, and changing its default SMB configurations to permit legacy null session communication.

