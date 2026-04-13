# Home SOC Lab (VMware, Kali Linux, and Windows 11)

## Summary
This project showcases a **home-built Security Operations Center (SOC) lab** using VMware. The lab simulates real-world cyber attacks from an attacker machine (Kali Linux) against a victim machine (Windows), with analysis performed like a security analyst.

The goal is to demonstrate **hands-on skills in detection, analysis, and reporting**—not just theoretical knowledge from Security+.

## Lab Architecture
- **Attacker:** Kali Linux (VM)
- **Victim:** Windows 11 (VM)
- **Host:** Windows laptop
- **Network:** Isolated (NAT / Host-only)

This setup allows safe simulation of attacks and analysis of logs without affecting real systems.

## Tools & Technologies Used
- VMware Workstation Pro
- Kali Linux
- Windows 11
- Nmap (network scanning)
- Wireshark (packet analysis)
- Windows Event Viewer (log analysis)

## Objectives
- Build an isolated virtual lab environment
- Simulate common attacks (port scanning, brute force, enumeration)
- Capture and analyze network traffic and system logs
- Detect suspicious behavior and indicators of compromise (IOCs)
- Write professional incident reports
