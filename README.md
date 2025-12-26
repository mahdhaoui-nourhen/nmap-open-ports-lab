# Nmap Open Service Ports Analysis Lab

## 1. Introduction
This laboratory work presents a practical exploration of **network reconnaissance** using the Nmap tool.  
The objective is to identify open ports, enumerate running services, detect operating system information, and analyze the exposed attack surface of a target system.

The lab was performed in a controlled virtual environment to ensure safe and ethical testing conditions.

---

## 2. Lab Environment
The following environment was used during this lab:

- **Attacker Machine:** Kali Linux  
- **Target Machine:** Metasploitable 2  
- **Virtualization Platform:** Oracle VirtualBox  
- **Network Type:** NAT Network  
- **Target IP Address:** 10.0.2.3  

This configuration allows secure communication between machines while isolating the lab from external networks.

---

## 3. Objectives
The main objectives of this lab are:
- Discover open TCP ports on a target machine
- Identify running network services and their versions
- Perform operating system fingerprinting
- Understand the concept of attack surface
- Analyze security risks associated with exposed services
- Propose mitigation and hardening measures

---

## 4. Tools and Technologies
- **Nmap:** Network scanning and reconnaissance tool  
- **Kali Linux:** Penetration testing operating system  
- **Metasploitable 2:** Intentionally vulnerable target machine  
- **VirtualBox:** Virtualization platform  

---

## 5. Methodology

### 5.1 Connectivity Verification
Before scanning, network connectivity between the attacker and target machines was verified.

```bash
ping -c 4 10.0.2.3
Successful replies confirmed proper network communication.
open Port Discovery

A basic Nmap scan was performed to identify open TCP ports
nmap 10.0.2.3
This scan revealed multiple open ports exposing different network services
5.3 Service Version Enumeration
To identify service names and software versions, the following command was used
nmap -sV 10.0.2.3
This step is critical for vulnerability assessment, as outdated services often contain known exploits.
5.4 Operating System Detection
Operating system fingerprinting was performed using:
nmap -O 10.0.2.3
Nmap successfully identified the target as a Linux-based system.
5.5 Aggressive Scan
A comprehensive scan combining multiple detection techniques was executed:
nmap -A 10.0.2.3
This scan included service detection, OS fingerprinting, default scripts, and traceroute.
6. Results and Findings
6.1 Open Ports
Several TCP ports were found open, including:
FTP (21)

SSH (22)

Telnet (23)

HTTP (80)

SMB (445)

MySQL (3306)

6.2 Running Services
The scan revealed multiple outdated services such as:

vsftpd 2.3.4

Apache HTTP Server

MySQL Database Service

These services are known to contain vulnerabilities if not properly secured
6.3 Operating System

The target machine was identified as a Linux-based operating system, consistent with the Metasploitable 2 configuration.
7. Security Risk Analysis

The exposed services significantly increase the attack surface:

FTP and Telnet transmit credentials in clear text

Outdated software versions may contain publicly known vulnerabilities

SMB services may allow lateral movement within a network

Exposed database services can lead to data leakage or unauthorized access
8. Security Recommendations

To reduce the attack surface, the following actions are recommended:

Disable unnecessary services

Close unused ports

Apply regular security updates and patches

Implement firewall filtering rules

Replace insecure protocols with secure alternatives (e.g., SSH instead of Telnet)
9. Screenshots

This repository includes screenshots demonstrating:

Network connectivity verification

Nmap scanning commands and results

Service version enumeration

Operating system detection
10. Conclusion

This lab highlights the importance of network reconnaissance in cybersecurity.
Identifying exposed services and outdated software is a critical step in understanding system vulnerabilities and improving overall security posture.

Regular scanning and proper system hardening are essential practices for defending against real-world attacks.
11. Keywords
Network Security, Nmap, Port Scanning, Service Enumeration, Attack Surface, Ethical Hacking

