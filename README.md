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

