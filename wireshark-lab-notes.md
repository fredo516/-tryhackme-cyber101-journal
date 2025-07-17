
# Wireshark Lab Notes

This file documents my hands-on experience using Wireshark during school labs and self-study.

---

## 🧠 Overview

Wireshark is a network protocol analyzer used to capture and inspect packets in real-time. I used it to analyze network traffic during cybersecurity coursework and lab exercises.

---

## 🔧 Lab Activities

### ✅ Packet Capture
- Captured live traffic on a local network using Wireshark's interface selection tool
- Applied filters such as `ip.addr == 192.168.1.1`, `http`, and `tcp.port == 80` to narrow traffic views

### ✅ Protocol Analysis
- Examined HTTP, DNS, ARP, TCP three-way handshakes
- Used the “Follow TCP Stream” feature to reassemble conversations
- Identified request/response behavior between client and server

### ✅ Suspicious Traffic Detection
- Practiced identifying brute force login attempts by analyzing repeated failed packets
- Detected ARP spoofing behavior using packet timing and sender/receiver mismatches

### ✅ Exporting & Reporting
- Exported filtered traffic to .pcap files for later analysis
- Documented findings in reports with packet screenshots and annotations

---

## 🛠️ Tools/Skills Used
- Wireshark display and capture filters
- TCP/IP protocol stack understanding
- Packet inspection and session reconstruction
- Traffic pattern recognition and anomaly detection

---

## 📌 Key Takeaways
- Developed baseline awareness of normal network behavior
- Gained practical experience in identifying patterns of network-based attacks
- Reinforced the importance of logging and monitoring at the packet level
