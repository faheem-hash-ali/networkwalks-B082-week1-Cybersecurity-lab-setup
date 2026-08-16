<div align="center">

# 🛡️ Practical Cybersecurity & Pentesting Lab Setup

### Isolated Virtual Environment for Hands-on Security Testing & Ethical Hacking

<br/>

![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-0F172A?style=for-the-badge&labelColor=EF4444&logo=securityscorecard&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Attacker%20OS-Kali%202026.2-0F172A?style=for-the-badge&labelColor=0EA5E9&logo=kalilinux&logoColor=white)
![VirtualBox](https://img.shields.io/badge/Hypervisor-VirtualBox%207.x-0F172A?style=for-the-badge&labelColor=2563EB&logo=virtualbox&logoColor=white)
![Network](https://img.shields.io/badge/Subnet-10.0.0.0%2F24-0F172A?style=for-the-badge&labelColor=0D9488&logo=wireshark&logoColor=white)
![Linux](https://img.shields.io/badge/Platform-Linux-0F172A?style=for-the-badge&labelColor=334155&logo=linux&logoColor=white)
![Penetration Testing](https://img.shields.io/badge/Practice-Pentesting-0F172A?style=for-the-badge&labelColor=7C3AED&logo=kalilinux&logoColor=white)
![Networkwalks](https://img.shields.io/badge/Program-Networkwalks%20B082-0F172A?style=for-the-badge&labelColor=1D4ED8)
![Mentor](https://img.shields.io/badge/Mentor-Waqas%20Karim%20(CCIE)-0F172A?style=for-the-badge&labelColor=475569)

<br/>

**Repository:** `networkwalks-B082-week1-Cybersecurity-lab-setup`  
*Virtualization • Network Isolation • Kali Linux • Network Troubleshooting*

---

</div>

## 📌 Executive Summary

Setting up a dedicated, segmented virtual laboratory is an essential pre-requisite for ethical hacking and vulnerability assessments. This repository documents the end-to-end deployment of an isolated lab environment using **Oracle VirtualBox** and **Kali Linux 2026.2**.

The lab architecture is structured to simulate a real-world enterprise subnet (`10.0.0.0/24`) while preventing unauthorized traffic leakage into production or host networks.

---

## ⚙️ Host & Environment Architecture

| Specification Parameter | System Configuration |
| :--- | :--- |
| **Host Operating System** | Windows 11 (64-bit) |
| **Host Processor (CPU)** | Intel Core i5 |
| **Host Physical Memory (RAM)** | 8 GB |
| **Host Storage** | 256 GB SSD |
| **Hypervisor Engine** | Oracle VM VirtualBox |
| **Attacker VM OS** | Kali Linux 2026.2 (Debian 64-bit) |
| **Attacker VM Resources** | 2048 MB RAM • 2 vCPUs |
| **Network Topology** | Isolated Custom NAT Network (`NatNetwork`) |
| **Subnet Addressing** | `10.0.0.0/24` (DHCP Enabled, IPv6 Disabled) |
| **Attacker IP Assignment** | `10.0.0.2/24` |
| **Default Gateway** | `10.0.0.1` |
| **Upstream DNS** | `8.8.8.8` (Google Public DNS) |

---

## 🗺️ Lab Network Topology

```text
       ┌──────────────────────────────────────────────┐
       │             Windows 11 Host OS               │
       └──────────────────────┬───────────────────────┘
                              │
                              ▼
       ┌──────────────────────────────────────────────┐
       │          Oracle VM VirtualBox Engine         │
       └──────────────────────┬───────────────────────┘
                              │
                              ▼
       ┌──────────────────────────────────────────────┐
       │     Isolated NAT Network [ 10.0.0.0/24 ]     │
       │     Gateway: 10.0.0.1  |  DNS: 8.8.8.8        │
       └──────────────────────┬───────────────────────┘
                              │
                              ▼
       ┌──────────────────────────────────────────────┐
       │       Kali Linux 2026.2 (Attacker VM)        │
       │       IP: 10.0.0.2/24  |  NIC: eth0          │
       └──────────────────────────────────────────────┘
