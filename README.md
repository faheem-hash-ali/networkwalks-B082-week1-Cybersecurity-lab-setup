<h1 align="center"> 💻 Cybersecurity Lab Environment Setup</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Cybersecurity-0F172A?style=for-the-badge&labelColor=2563EB&logo=kalilinux&logoColor=white" alt="Cybersecurity" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-111827?style=for-the-badge&labelColor=0EA5E9&logo=kalilinux&logoColor=white" alt="Kali Linux" />
  <img src="https://img.shields.io/badge/VirtualBox-v7.x-111827?style=for-the-badge&labelColor=2563EB&logo=virtualbox&logoColor=white" alt="VirtualBox" />
  <img src="https://img.shields.io/badge/Linux-111827?style=for-the-badge&labelColor=475569&logo=linux&logoColor=white" alt="Linux" />
  <img src="https://img.shields.io/badge/Networking-111827?style=for-the-badge&labelColor=0891B2" alt="Networking" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-111827?style=for-the-badge&labelColor=7C3AED&logo=kalilinux&logoColor=white" alt="Penetration Testing" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-111827?style=for-the-badge&labelColor=4F46E5&logo=kalilinux&logoColor=white" alt="Ethical Hacking" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-111827?style=for-the-badge&labelColor=0891B2" alt="Network" />
  <img src="https://img.shields.io/badge/Virtualization-111827?style=for-the-badge&labelColor=2563EB&logo=virtualbox&logoColor=white" alt="Virtualization" />
  <img src="https://img.shields.io/badge/Networkwalks-111827?style=for-the-badge&labelColor=2563EB" alt="Networkwalks" />
  <img src="https://img.shields.io/badge/Mentor-Waqas%20Karim%20(CCIE)-111827?style=for-the-badge&labelColor=475569" alt="Waqas Karim CCIE" />
</p>

<p align="center">
  <strong>networkwalks-B082-week1-Cybersecurity-lab-setup</strong>
</p>

<p align="center">
  VirtualBox • Kali Linux • Virtual Networking • Linux Networking
</p>

<hr />

<h1>🎯 Lab Purpose</h1>

<p>The purpose of this lab is to build a <strong>controlled and isolated cybersecurity environment</strong> using Oracle VirtualBox and Kali Linux.</p>

<p>A dedicated virtual lab provides a safer environment for practicing cybersecurity concepts without directly experimenting on production systems or unauthorized networks.</p>

<p>The lab will be used as a foundation for practical learning in:</p>

<ul>
  <li>Networking</li>
  <li>Linux</li>
  <li>Cisco</li>
  <li>Ethical Hacking</li>
  <li>VAPT</li>
  <li>Security Labs</li>
  <li>Python</li>
  <li>Security Automation</li>
</ul>

<hr />

<h1>🖥️ Lab Environment</h1>

<table>
  <thead>
    <tr>
      <th>Component</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Host Operating System</td>
      <td>Windows 11</td>
    </tr>
    <tr>
      <td>Processor</td>
      <td>Intel Core i5</td>
    </tr>
    <tr>
      <td>RAM</td>
      <td>8 GB</td>
    </tr>
    <tr>
      <td>Storage</td>
      <td>256 GB SSD</td>
    </tr>
    <tr>
      <td>Virtualization Platform</td>
      <td>Oracle VirtualBox</td>
    </tr>
    <tr>
      <td>Guest Operating System</td>
      <td>Kali Linux 2026.2</td>
    </tr>
    <tr>
      <td>VM Allocated RAM</td>
      <td>2048 MB (2 GB)</td>
    </tr>
    <tr>
      <td>VM Allocated Cores</td>
      <td>2 CPU Cores</td>
    </tr>
    <tr>
      <td>Network Type</td>
      <td>NAT Network (<code>NatNetwork</code>)</td>
    </tr>
    <tr>
      <td>Network CIDR</td>
      <td>10.0.0.0/24</td>
    </tr>
    <tr>
      <td>Kali Linux IP</td>
      <td>10.0.0.2/24 (via DHCP)</td>
    </tr>
    <tr>
      <td>Gateway</td>
      <td>10.0.0.1</td>
    </tr>
    <tr>
      <td>DNS</td>
      <td>8.8.8.8</td>
    </tr>
  </tbody>
</table>

<hr />

<h1>🔗 Tools &amp; Resources</h1>

<ul>
  <li><strong>7-Zip:</strong> <a href="https://7-zip.org/download.html">https://7-zip.org/download.html</a></li>
  <li><strong>VirtualBox:</strong> <a href="https://virtualbox.org/wiki/Downloads">https://virtualbox.org/wiki/Downloads</a></li>
  <li><strong>Kali Linux:</strong> <a href="https://kali.org/get-kali">https://kali.org/get-kali</a></li>
</ul>

<hr />

<h1>📝 Steps 1/6</h1>

<ul>
  <li>7-Zip</li>
  <li>Oracle VirtualBox</li>
  <li>NAT Network</li>
  <li>Kali Linux VM Setup</li>
  <li>Kali Linux Network Configuration &amp; Troubleshooting</li>
  <li>VirtualBox Snapshots</li>
</ul>

<hr />

<h1>🛡️ Lab Setup</h1>

<p>The Networkwalks Phase 1 workflow consists of six setup steps:</p>

<ol>
  <li>Install 7-Zip</li>
  <li>Install Oracle VirtualBox</li>
  <li>Configure the VirtualBox NAT Network</li>
  <li>Download and import Kali Linux</li>
  <li>Configure Kali Linux IP settings &amp; resolve network disconnection</li>
  <li>Create a VM snapshot</li>
</ol>

<hr />
<hr />

<h1>🚀 Phase 01 — Lab Setup</h1>

<h2>1️⃣ 7-Zip Installation</h2>

<h3>What I Did</h3>
<p>Installed <strong>7-Zip</strong> on Windows 11 to extract and manage virtual machine compressed archives.</p>

<h3>Why</h3>
<p>The Kali Linux virtual machine files require extraction before importing into the VirtualBox hypervisor.</p>

<h3>Result</h3>
<p><strong>Status:</strong> ✅ Completed</p>

<hr />

<h2>2️⃣ Oracle VirtualBox Installation</h2>

<h3>What I Did</h3>
<p>Installed and configured <strong>Oracle VirtualBox</strong> as the primary virtualization engine on Windows 11.</p>

<h3>Why</h3>
<p>VirtualBox provides the hypervisor environment to deploy, run, and isolate the Kali Linux machine safely.</p>

<h3>Result</h3>
<p><strong>Status:</strong> ✅ Completed</p>

<hr />

<h2>3️⃣ NAT Network Configuration</h2>

<h3>What I Did</h3>
<p>Created a custom <strong>NAT Network</strong> named <code>NatNetwork</code> within VirtualBox Global Network Preferences.</p>

<h3>Why</h3>
<p>To establish a dedicated, isolated subnet for the lab virtual machines with DHCP enabled and IPv6 disabled to avoid interface conflicts.</p>

<pre><code>Network Type : NAT Network
Network Name : NatNetwork
Network CIDR : 10.0.0.0/24
DHCP         : Enabled
IPv6         : Disabled</code></pre>

<h3>Result</h3>
<p><strong>Status:</strong> ✅ Completed</p>
<p align="center">
  <img src="Screenshot-Virtual_box-Network-Setting.png" alt="VirtualBox NAT Network Configuration" width="100%" />
</p>

<hr />

<h2>4️⃣ Kali Linux VM Setup</h2>

<h3>What I Did</h3>
<p>Imported <strong>Kali Linux 2026.2</strong> into VirtualBox, allocated hardware resources, and attached Adapter 1 to <code>NatNetwork</code>.</p>

<h3>Why</h3>
<p>Kali Linux acts as the primary attacker environment for penetration testing and network security practice.</p>

<h3>VM Configuration</h3>
<pre><code>Operating System : Kali Linux 2026.2 (Debian 64-bit)
Allocated Memory : 2048 MB (2 GB)
Allocated CPU    : 2 Processors
Network Adapter  : NAT Network (NatNetwork)
Promiscuous Mode : Allow All</code></pre>

<h3>Result</h3>
<p><strong>Status:</strong> ✅ Completed</p>
<p align="center">
  <img src="Screenshot-Kali_Machine-Details.png" alt="Kali Linux Hardware Configuration" width="100%" />
</p>
<p align="center">
  <img src="VirtualBox_kali-linux-2026.2-virtualbox-Lab-Setup.jpg" alt="Kali Linux Lab Desktop Environment" width="100%" />
</p>

<hr />

<h2>5️⃣ Kali Linux Network Configuration &amp; Troubleshooting</h2>

<h3>What I Did</h3>
<p>Configured the <code>eth0</code> network interface parameters and resolved the persistent network disconnection issue on Kali Linux 2026.2.</p>

<h3>Why</h3>
<p>Ensures stable communication across the NAT Network subnet (<code>10.0.0.0/24</code>) and maintains permanent upstream internet connectivity without connection drops.</p>

<h3>Network Settings</h3>
<pre><code>Interface  : eth0 (Wired connection 1)
IP Address : 10.0.0.2/24
Gateway    : 10.0.0.1
DNS        : 8.8.8.8</code></pre>

<p align="center">
  <img src="Screenshot-Kali-Machine-Network-Setting.png" alt="Kali Linux Network Settings" width="100%" />
</p>

<h3>Troubleshooting: DAD Timeout Disconnection Fix</h3>
<p>During runtime, <code>eth0</code> continuously lost internet connectivity due to Duplicate Address Detection (DAD) delay flags. Solved permanently using:</p>

<pre><code class="language-bash"># Set DAD timeout to 0 on Wired connection 1
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

# Ping test verification to Google DNS
ping google.com</code></pre>

<p align="center">
  <img src="Screenshot-ping_google.com.png" alt="ICMP Ping Verification" width="100%" />
</p>

<h3>Result</h3>
<p><strong>Status:</strong> ✅ Completed</p>

<hr />

<h2>6️⃣ VirtualBox Snapshot</h2>

<h3>What I Did</h3>
<p>Created a clean <strong>VirtualBox Snapshot</strong> named <code>1st week snapshot</code> after completing and verifying the network configuration.</p>

<h3>Why</h3>
<p>Provides an uncorrupted rollback baseline to restore the VM state before running security assessments or lab simulations.</p>

<h3>Snapshot Purpose</h3>
<pre><code>Snapshot Name    : 1st week snapshot
Snapshot Purpose : Lab Backup &amp; Disaster Recovery</code></pre>

<h3>Result</h3>
<p><strong>Status:</strong> ✅ Completed</p>

<hr />

<h1>🏗️ Lab Architecture</h1>

<pre><code>Host Machine (Windows 11)
        │
        ▼
Oracle VirtualBox
        │
        ▼
NAT Network (10.0.0.0/24)
Gateway: 10.0.0.1  |  DNS: 8.8.8.8
        │
        ▼
Kali Linux 2026.2 VM
IP: 10.0.0.2/24  (eth0)
        │
        ▼
Cybersecurity Labs</code></pre>

<hr />

<h1>🧠 Key Learning</h1>

<p>During this setup, I gained practical hands-on experience with:</p>

<ul>
  <li>Virtualization and hypervisor resource allocation</li>
  <li>VirtualBox custom NAT Network configuration</li>
  <li>Kali Linux 2026.2 deployment and optimization</li>
  <li>IPv4 subnetting and DNS configuration</li>
  <li>Troubleshooting Linux NetworkManager and resolving DAD timeout issues via <code>nmcli</code></li>
  <li>Connectivity testing using ICMP echo requests</li>
  <li>VirtualBox snapshot creation and state recovery</li>
</ul>

<hr />

<h1>🔐 Security &amp; Ethics</h1>

<p>This virtual laboratory is built strictly for <strong>educational and authorized cybersecurity learning purposes</strong>.</p>

<p>Security testing and assessments should only be conducted on systems, networks, or applications that you own or have explicit written permission to evaluate.</p>

<hr />

<h1>👨‍🏫 Mentor</h1>

<p><strong>Waqas Karim (CCIE)</strong></p>

<p>Thank you for the guidance and practical learning blueprints throughout the lab setup.</p>

<hr />

<h1>📊 Phase 01 Progress</h1>

<p><strong>6 / 6 Steps Completed ✅</strong></p>

<blockquote>
  <p>🔐 <strong>Learn • Practice • Build • Secure</strong></p>
</blockquote>

<p><strong>Networkwalks Cybersecurity Internship — Week 01</strong></p>
