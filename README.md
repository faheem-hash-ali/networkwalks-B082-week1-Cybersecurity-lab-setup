<div align="center">

# 🛡️ Enterprise Virtual Lab Setup for Penetration Testing & Ethical Hacking

### Practical Implementation of an Isolated Network Architecture using Oracle VirtualBox & Kali Linux 2026.2

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
*Virtualization • Network Segmentation • NetworkManager Optimization • Kernel Packet Capturing*

---

</div>

<br/>

## 📖 Table of Contents
1. [Project Overview & Lab Objectives](#-project-overview--lab-objectives)
2. [Hardware & Virtualization Environment](#-hardware--virtualization-environment)
3. [Network Topology & Architecture Plan](#-network-topology--architecture-plan)
4. [Step-by-Step Implementation Roadmap](#-step-by-step-implementation-roadmap)
   - [Phase 1: Hypervisor Deployment & NAT Network Construction](#phase-1-hypervisor-deployment--nat-network-construction)
   - [Phase 2: Attacker Machine Deployment (Kali Linux 2026.2)](#phase-2-attacker-machine-deployment-kali-linux-20262)
   - [Phase 3: Network Interface & DNS Configuration](#phase-3-network-interface--dns-configuration)
   - [Phase 4: Network Troubleshooting (DAD Timeout Fix)](#phase-4-network-troubleshooting-dad-timeout-fix)
   - [Phase 5: Routing Verification & Baseline State Management](#phase-5-routing-verification--baseline-state-management)
5. [Key Technical Learnings](#-key-technical-learnings)
6. [Security & Ethical Standards](#-security--ethical-standards)
7. [Acknowledgments & Mentorship](#-acknowledgments--mentorship)

---

<br/>

## 🎯 Project Overview & Lab Objectives

In offensive security and vulnerability research, practicing directly on live or public infrastructure introduces extreme risks of operational interruption, data exposure, and legal violations. A segmented virtual laboratory is an essential industry prerequisite for simulating real-world threat scenarios.

### Core Objectives:
* **Network Isolation:** Create an isolated VirtualBox NAT Network (`10.0.0.0/24`) that allows outbound connectivity for security updates while containing internal broadcast traffic.
* **Attacker Machine Provisioning:** Deploy and optimize **Kali Linux 2026.2** with appropriate CPU, RAM, and storage allocations.
* **Network Troubleshooting:** Address and permanently fix underlying Linux NetworkManager issues related to Duplicate Address Detection (DAD) timeouts over virtual bridged adapters.
* **Disaster Recovery & Snapshotting:** Establish a safe, reversible baseline snapshot prior to executing vulnerability assessments and security tooling.

---

<br/>

## 💻 Hardware & Virtualization Environment

### Host Machine Specifications (Lenovo Host)
* **Host Operating System:** Microsoft Windows 11 (64-bit)
* **Processor (CPU):** Intel Core i5 (Multi-core Virtualization Enabled - Intel VT-x)
* **Physical System RAM:** 8 GB DDR4
* **Storage Drive:** 256 GB NVMe Solid State Drive (SSD)
* **Hypervisor:** Oracle VM VirtualBox (v7.x)

### Virtual Machine Resource Allocation (Kali Linux 2026.2)
* **Base Memory (RAM):** 2048 MB (2.0 GB)
* **Virtual CPU Cores:** 2 Processors (Nested Paging, PAE/NX, KVM Paravirtualization)
* **Storage Allocation:** 80.09 GB Dynamic VDI (`kali-linux-2026.2-virtualbox-amd64.vdi`)
* **Network Interface:** Intel PRO/1000 MT Desktop (Attached to `NatNetwork`)
* **Promiscuous Mode:** `Allow All` (Ensures full raw packet inspection for sniffing tools)

---

<br/>

## 🌐 Network Topology & Architecture Plan

```text
               ┌─────────────────────────────────────────────────────────┐
               │                Host OS: Windows 11                      │
               │         Physical Connectivity & Hypervisor Layer        │
               └────────────────────────────┬────────────────────────────┘
                                            │
                                            ▼
               ┌─────────────────────────────────────────────────────────┐
               │               Oracle VM VirtualBox Engine               │
               │               Virtual Networking Driver                 │
               └────────────────────────────┬────────────────────────────┘
                                            │
                                            ▼
               ┌─────────────────────────────────────────────────────────┐
               │       Segmented NAT Network: 10.0.0.0/24 (NatNetwork)   │
               │       Gateway: 10.0.0.1  |  DHCP Range: 10.0.0.0/24     │
               └────────────────────────────┬────────────────────────────┘
                                            │
                                            ▼
               ┌─────────────────────────────────────────────────────────┐
               │             Primary Attacker Machine                    │
               │             Kali Linux 2026.2 (Debian)                  │
               │             IP: 10.0.0.2/24 | DNS: 8.8.8.8              │
               └─────────────────────────────────────────────────────────┘
