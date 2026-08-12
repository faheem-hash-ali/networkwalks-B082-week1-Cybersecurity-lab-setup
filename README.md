# Networkwalks B082 - Week 1: Cybersecurity Lab Setup

## Overview
This repository contains the complete documentation, configuration details, and verification steps for setting up a practical Cybersecurity & Ethical Hacking virtual lab environment on Oracle VirtualBox.

---

## 🛠️ Environment Architecture & Specs
- **Hypervisor:** Oracle VirtualBox
- **Host OS:** Windows 11
- **Primary Attacker VM:** Kali Linux 2026.2
- **Network Mode:** Custom NAT Network (`NatNetwork`)
- **Subnet/IP Range:** `10.0.0.0/24`

---

## 📋 Step-by-Step Implementation

### Phase 1: VirtualBox Network & VM Configuration
1. **Global NAT Network Creation:**
   - Created a custom NAT Network named `NatNetwork`.
   - Set IPv4 Prefix to `10.0.0.0/24` with DHCP enabled.
   - Disabled IPv6 to prevent routing and interface conflicts.

2. **Kali Linux 2026.2 VM Setup:**
   - Allocated recommended CPU cores and RAM (2048 MB).
   - Set Network Adapter 1 to `NAT Network` attached to `NatNetwork`.
   - Configured Promiscuous Mode to `Allow All` for lab packet analysis.

---

### Phase 2: Network Troubleshooting & Issue Resolution
1. **Fixing Frequent Internet Disconnection Issue:**
   - Encountered continuous network drops/disconnections on Kali Linux 2026.2 due to Duplicate Address Detection (DAD) timeout conflicts on VirtualBox.
   - Resolved the disconnection issue permanently by setting the DAD timeout to `0` using `nmcli`:
     ```bash
     sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
     ```
   - Reconnected the interface to establish a stable and uninterrupted internet connection across the lab environment.

---

## 📜 Credits & Acknowledgments
Special thanks to **Networkwalks Academy** and instructor **Waqas Karim (CCIE)** for the lab guidance and practical workflow.
