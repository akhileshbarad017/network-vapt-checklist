<p align="center">
  <img src="https://img.shields.io/badge/Network-VAPT-red?style=for-the-badge&logo=hackthebox" />
  <img src="https://img.shields.io/badge/OSI-L2_to_L7-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Version-2.0-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" />
</p>

<h1 align="center">🔐 Network VAPT Checklist</h1>

<p align="center">
  <b>A comprehensive, battle-tested Vulnerability Assessment & Penetration Testing checklist for network security assessments.</b><br>
  <i>From Layer 2 Switch Security to Active Directory Exploitation — covering everything a modern network pentester needs.</i>
</p>

---

## 📖 Table of Contents

- [🚀 Quick Start](#-quick-start)
- [⚠️ Disclaimer](#️-disclaimer)
- [📋 Phase 1: Pre-Engagement](#-phase-1-pre-engagement)
- [📋 Phase 2: Reconnaissance & OSINT](#-phase-2-reconnaissance--osint)
- [📋 Phase 3: Host Discovery](#-phase-3-host-discovery)
- [📋 Phase 4: OS Fingerprinting](#-phase-4-os-fingerprinting)
- [📋 Phase 5: Advanced TCP/IP Stack Testing](#-phase-5-advanced-tcpip-stack-testing)
- [📋 Phase 6: Port Scanning & Service Enumeration](#-phase-6-port-scanning--service-enumeration)
- [📋 Phase 7: Vulnerability Scanning](#-phase-7-vulnerability-scanning)
- [📋 Phase 8: Service-Specific Testing](#-phase-8-service-specific-testing)
- [📋 Phase 9: SSL/TLS Auditing](#-phase-9-ssltls-auditing)
- [📋 Phase 10: Default Credentials Check](#-phase-10-default-credentials-check)
- [📋 Phase 11: Firewall & IDS/IPS Evasion](#-phase-11-firewall--idsips-evasion)
- [📋 Phase 12: Layer 2 Switch Security](#-phase-12-layer-2-switch-security)
- [📋 Phase 13: Network Protocol Attacks](#-phase-13-network-protocol-attacks)
- [📋 Phase 14: DHCP Security](#-phase-14-dhcp-security)
- [📋 Phase 15: ARP Security](#-phase-15-arp-security)
- [📋 Phase 16: Routing Protocol Security](#-phase-16-routing-protocol-security)
- [📋 Phase 17: MPLS & VRF Testing](#-phase-17-mpls--vrf-testing)
- [📋 Phase 18: Multicast Security](#-phase-18-multicast-security)
- [📋 Phase 19: IPv6 Network Testing](#-phase-19-ipv6-network-testing)
- [📋 Phase 20: Network Segmentation Validation](#-phase-20-network-segmentation-validation)
- [📋 Phase 21: NDR Evasion & Stealth](#-phase-21-ndr-evasion--stealth)
- [📋 Phase 22: Password Attacks & Hash Cracking](#-phase-22-password-attacks--hash-cracking)
- [📋 Phase 23: Active Directory Testing](#-phase-23-active-directory-testing)
- [📋 Phase 24: Exploitation & Post-Exploitation](#-phase-24-exploitation--post-exploitation)
- [📋 Phase 25: Reporting](#-phase-25-reporting)
- [🛠️ Tools Reference](#️-tools-reference)
- [⚡ One-Liners Cheat Sheet](#-one-liners-cheat-sheet)
- [📊 Severity Classification](#-severity-classification)
- [🏛️ Compliance Mapping](#️-compliance-mapping)
- [📁 Repo Structure](#-repo-structure)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

---

## 🚀 Quick Start

```bash
# 1. Clone this repo for reference
git clone https://github.com/yourusername/network-vapt-checklist.git

# 2. Prepare your environment (Kali Linux recommended)
sudo apt update && sudo apt install -y nmap masscan nikto sslscan

# 3. Start with Phase 2 (Recon) → Phase 3 (Discovery) → Phase 6 (Scanning)
# Follow the checklist sequentially. Tick [x] as you complete each item.

# 4. Document everything in the reports/ folder
```

> 💡 **Pro Tip:** Don't skip Phase 5 (TCP/IP Stack) and Phase 12 (Layer 2). These are where most testers miss critical findings.

---

## ⚠️ Disclaimer

> **This checklist is intended for AUTHORIZED penetration testing only.**
> 
> Always obtain **written permission** before testing any network or system. Unauthorized access to computer systems is illegal under various cybercrime laws including the IT Act, Computer Fraud and Abuse Act (CFAA), and similar legislation worldwide.
>
> **The authors assume no liability for any misuse or damage caused by this material.**

---

## 📋 Phase 1: Pre-Engagement

> 🎯 **Goal:** Define boundaries, get legal coverage, and plan the attack.

| # | Task | Severity |
|---|------|----------|
| [ ] | Define scope — IP ranges, subnets, devices in scope | Critical |
| [ ] | Identify out-of-scope assets and restricted areas | Critical |
| [ ] | Obtain **written authorization** / signed Rules of Engagement (RoE) | Critical |
| [ ] | Define testing type: Black Box / Grey Box / White Box | High |
| [ ] | Set testing timeframe to minimize business disruption | High |
| [ ] | Review compliance requirements (PCI-DSS, ISO 27001, HIPAA, GDPR, NIST) | High |
| [ ] | Collect network architecture documentation (if White Box) | Medium |
| [ ] | Identify business-critical services to avoid disruption | Critical |
| [ ] | Set up VPN/jump host if required | Medium |
| [ ] | Prepare test environment and tools (Kali Linux, Metasploit, Nessus) | Medium |
| [ ] | Establish emergency contact with client | Critical |
| [ ] | Define success criteria and deliverables | Medium |

---

## 📋 Phase 2: Reconnaissance & OSINT

> 🎯 **Goal:** Gather intelligence without touching the target network.

### 🔍 Manual Recon

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | WHOIS lookup | `whois` | Info |
| [ ] | DNS record enumeration (A, MX, NS, TXT, SOA, AAAA) | `dig`, `nslookup` | Info |
| [ ] | Full DNS enumeration + AXFR attempt | `dnsrecon` | Medium |
| [ ] | Shodan search for exposed services | [shodan.io](https://shodan.io) | High |
| [ ] | Censys / Fofa / Zoomeye search | Web | High |
| [ ] | Google dorking for exposed files, panels, configs | Google | Medium |
| [ ] | Identify email format and employee names | LinkedIn, Hunter.io | Info |
| [ ] | Check for credential leaks | HaveIBeenPwned, DeHashed | High |
| [ ] | Certificate Transparency log search | crt.sh, Censys | Medium |
| [ ] | ASN and IP range discovery | `metabigor`, BGP_HE | Info |
| [ ] | Subdomain discovery | `reconftw`, `AORT`, `gobuster` | Medium |
| [ ] | SMTP user enumeration (VRFY/EXPN/RCPT) | `smtp-user-enum` | Medium |
| [ ] | Fast port/service discovery | `skanuvaty`, `Dismap` | Medium |
| [ ] | Full automated OSINT | `SpiderFoot` | Medium |

### 🤖 Automated OSINT

```bash
# SpiderFoot — 200+ OSINT sources
pip3 install spiderfoot
python3 sf.py -l 127.0.0.1:5001

# reconftw — Full-chain automated recon
git clone https://github.com/six2dez/reconftw && cd reconftw && ./install.sh
./reconftw.sh -d <target-domain> -r

# AORT — All-in-One Recon Tool
git clone https://github.com/D3Ext/AORT && cd AORT
python3 aort.py -d <target-domain>
```

---

## 📋 Phase 3: Host Discovery

> 🎯 **Goal:** Find all live hosts in the target scope.

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Nmap ping sweep (host discovery only) | `nmap -sn` | Info |
| [ ] | ARP scan for local network | `arp-scan`, `netdiscover` | Info |
| [ ] | ICMP echo sweep | `ping`, `fping` | Info |
| [ ] | TCP SYN host discovery (firewall evasion) | `nmap -PS` | Info |
| [ ] | UDP host discovery | `nmap -PU` | Info |
| [ ] | Custom packet crafting | `hping3` | Info |
| [ ] | Passive host discovery (no packets sent) | `p0f`, `netdiscover -p` | Info |
| [ ] | Document all live hosts with IP, MAC, and hostname | Manual | Info |

---

## 📋 Phase 4: OS Fingerprinting

> 🎯 **Goal:** Identify operating systems for targeted exploitation.

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Nmap OS detection | `nmap -O` | Info |
| [ ] | Aggressive scan (OS + version + scripts) | `nmap -A` | Info |
| [ ] | Banner grabbing via Netcat | `nc -nv` | Info |
| [ ] | Banner grabbing via Telnet | `telnet` | Info |
| [ ] | Passive OS fingerprinting | `p0f` | Info |
| [ ] | Identify OS type, version, kernel | `nmap`, manual | Info |
| [ ] | Map OS versions to known CVEs | Vulners, Exploit-DB | High |

---

## 📋 Phase 5: Advanced TCP/IP Stack Testing

> 🎯 **Goal:** Find anomalies in the network stack that bypass security controls.
> 🔥 **Often missed by junior testers. High impact findings live here.**

### 🔗 IP Spoofing & Source Routing

| # | Task | Command | Severity |
|---|------|---------|----------|
| [ ] | Loose Source Route test | `nmap --ip-options "L ..."` | High |
| [ ] | Strict Source Route test | `nmap --ip-options "R ..."` | High |
| [ ] | Firewall source routing block check | `hping3 --ip-options` | High |
| [ ] | IP spoofing acceptance test | `hping3 --spoof` | Critical |

### 🧬 TCP/IP Stack Fingerprinting

| # | Task | Command | Severity |
|---|------|---------|----------|
| [ ] | TCP ISN prediction | `nmap -O --osscan-guess` | Medium |
| [ ] | TCP Timestamp analysis | `nmap --script=timestamp` | Info |
| [ ] | IPID sequence analysis (Idle scan prep) | `nmap -sI` | Medium |
| [ ] | Passive OS fingerprinting | `p0f -i eth0` | Info |
| [ ] | TCP Window Size analysis | Wireshark | Info |
| [ ] | TCP Urgent Pointer testing | Custom | Low |

### 💥 Fragmentation & Reassembly Attacks

| # | Task | Command | Severity |
|---|------|---------|----------|
| [ ] | Tiny Fragment Attack | `nmap -f -f` | High |
| [ ] | Overlapping Fragment (Teardrop variant) | `hping3 -x` | High |
| [ ] | Custom fragment offset crafting | Scapy | High |
| [ ] | Firewall reassembly behavior test | Custom | High |

---

## 📋 Phase 6: Port Scanning & Service Enumeration

> 🎯 **Goal:** Map the entire attack surface.

| # | Task | Command | Severity |
|---|------|---------|----------|
| [ ] | Full TCP SYN Scan (all 65535 ports) | `nmap -Pn -p- -sS -sV` | Info |
| [ ] | Ultra-fast full port scan | `masscan -p1-65535` | Info |
| [ ] | Top 1000 UDP Ports Scan | `nmap -sU --top-ports=1000` | Info |
| [ ] | Script scan + version detection | `nmap -sC -sV` | Info |
| [ ] | SSH cipher enumeration | `nmap --script=ssh2-enum-algos` | Medium |
| [ ] | SSL cipher enumeration | `nmap --script=ssl-enum-ciphers` | Medium |
| [ ] | Export results (normal + grepable + XML) | `nmap -oN -oG -oX` | Info |
| [ ] | Service version → CVE mapping | Vulners, manual | High |
| [ ] | Load balancer detection | `lbd` | Info |
| [ ] | Session persistence testing | Manual | Medium |
| [ ] | SSL offloading misconfiguration | `testssl.sh` | Medium |

---

## 📋 Phase 7: Vulnerability Scanning

> 🎯 **Goal:** Automate vulnerability discovery and validate findings.

### Nessus / OpenVAS

| # | Task | Severity |
|---|------|----------|
| [ ] | Update plugins before scan | Critical |
| [ ] | Disable DoS test plugins (unless permitted) | Critical |
| [ ] | Enable both TCP + UDP scanning | High |
| [ ] | Run scan with assessment policy appropriate for scope | High |
| [ ] | Export report in PDF, CSV, and XML | Medium |
| [ ] | Manually validate each critical/high finding | Critical |
| [ ] | Map CVEs to CVSS v3.1 scores | High |
| [ ] | Verify false positives before reporting | Critical |

### Nuclei

```bash
# Install
go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest

# Network + CVE + Default Logins + Misconfiguration
nuclei -target <target-ip> -t network/ -t cves/ -t default-logins/ -t misconfiguration/

# Critical/High only
nuclei -target <target-ip> -severity critical,high

# HTTP services
nuclei -u http://<target-ip> -t exposed-panels/ -t default-logins/
```

---

## 📋 Phase 8: Service-Specific Testing

> 🎯 **Goal:** Deep-dive into each open service.

### FTP (21)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap FTP scripts | Medium |
| [ ] | Anonymous login test | High |
| [ ] | Directory traversal permissions | Medium |
| [ ] | FTP bounce attack | Medium |
| [ ] | Plaintext credential transmission | High |

### SSH (22)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap SSH scripts | Medium |
| [ ] | Weak/deprecated algorithms (MD5, CBC, arcfour) | High |
| [ ] | Username enumeration | Medium |
| [ ] | SSH version CVE mapping | High |
| [ ] | Default/weak credentials | Critical |

### SMTP (25)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap SMTP scripts | Medium |
| [ ] | VRFY / EXPN user enumeration | Medium |
| [ ] | Open relay check | Critical |
| [ ] | Server banner version disclosure | Low |

### DNS (53)
| # | Task | Severity |
|---|------|----------|
| [ ] | Zone transfer (AXFR) attempt | High |
| [ ] | DNS enumeration | Medium |
| [ ] | Subdomain brute force | Medium |
| [ ] | DNS cache poisoning risk | High |
| [ ] | DNSSEC validation check | Medium |

### HTTP/HTTPS (80/443)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nikto web server scan | Medium |
| [ ] | Dangerous HTTP methods (PUT, DELETE, TRACE) | High |
| [ ] | Missing security headers | Medium |
| [ ] | Default admin credentials (Tomcat, Jenkins, Webmin) | Critical |
| [ ] | Server version disclosure | Low |
| [ ] | Outdated web server software → CVE mapping | High |

### SMB (139/445)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap SMB scripts | Medium |
| [ ] | Enumerate SMB shares | High |
| [ ] | EternalBlue (MS17-010) | Critical |
| [ ] | SMB signing status | High |
| [ ] | Null session access | High |
| [ ] | SMBv1 enabled | Critical |

### SNMP (161 UDP)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap SNMP scripts | Medium |
| [ ] | Community string brute force | High |
| [ ] | SNMP data enumeration | High |
| [ ] | Default communities (public/private/manager) | Critical |
| [ ] | Device info, processes, interfaces | Medium |

### RDP (3389)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap RDP scripts | Medium |
| [ ] | NLA disabled | High |
| [ ] | MS12-020 (DoS) | Medium |
| [ ] | BlueKeep (CVE-2019-0708) | Critical |
| [ ] | Weak credentials | Critical |
| [ ] | RDP encryption config (CredSSP, TLS) | High |

### MSSQL (1433)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap MSSQL scripts | Medium |
| [ ] | Default credentials (sa:password) | Critical |
| [ ] | xp_cmdshell enabled | Critical |
| [ ] | Database enumeration | Medium |

### MySQL (3306)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap MySQL scripts | Medium |
| [ ] | Default credentials (root:root) | Critical |
| [ ] | Remote root access | Critical |
| [ ] | Database enumeration | Medium |

### Oracle (1521)
| # | Task | Severity |
|---|------|----------|
| [ ] | Nmap Oracle scripts | Medium |
| [ ] | SID brute force | High |
| [ ] | Default credentials | Critical |
| [ ] | Listener enumeration | Medium |

### NFS (2049)
| # | Task | Severity |
|---|------|----------|
| [ ] | NFS shares enumeration | High |
| [ ] | World-writable shares | High |
| [ ] | no_root_squash check | Critical |
| [ ] | Unauthorized mount access | High |

### TFTP (69 UDP)
| # | Task | Severity |
|---|------|----------|
| [ ] | TFTP anonymous access | High |
| [ ] | Sensitive file exposure | High |

### Telnet (23)
| # | Task | Severity |
|---|------|----------|
| [ ] | Banner grabbing | Low |
| [ ] | Cleartext credentials | Critical |
| [ ] | Default/weak credentials | Critical |
| [ ] | Telnet should be replaced by SSH | Medium |

### VNC (5900+)
| # | Task | Severity |
|---|------|----------|
| [ ] | VNC authentication check | Medium |
| [ ] | Blank/no password | Critical |
| [ ] | Weak credentials | Critical |

### X11 (6000+)
| # | Task | Severity |
|---|------|----------|
| [ ] | X11 unauthorized access | High |
| [ ] | X11 forwarding misconfiguration | Medium |

### rsync (873)
| # | Task | Severity |
|---|------|----------|
| [ ] | rsync anonymous access | High |
| [ ] | Module listing | Medium |
| [ ] | Unauthorized file sync | High |

### RPCbind (111)
| # | Task | Severity |
|---|------|----------|
| [ ] | RPC services enumeration | Medium |
| [ ] | Exposed RPC services | High |

### NTP (123 UDP)
| # | Task | Severity |
|---|------|----------|
| [ ] | NTP version detection | Info |
| [ ] | NTP amplification (DDoS risk) | High |
| [ ] | NTP monlist vulnerability | High |

### VoIP / SIP (5060)
| # | Task | Severity |
|---|------|----------|
| [ ] | SIP enumeration | Medium |
| [ ] | SIP user enumeration | Medium |
| [ ] | SIP brute force | High |
| [ ] | RTP stream capture | High |
| [ ] | VoIP VLAN hopping | High |
| [ ] | SRTP/TLS enforcement | Medium |

### VPN Protocols
| # | Task | Severity |
|---|------|----------|
| [ ] | **IPSec/IKE** — Aggressive mode check | Critical |
| [ ] | **IPSec/IKE** — Weak PSK | High |
| [ ] | **PPTP** — MS-CHAPv2 weakness | Critical |
| [ ] | **OpenVPN** — TLS auth bypass | High |
| [ ] | **WireGuard** — Unauthorized peer | Medium |
| [ ] | **SSL VPN** — Split tunneling misconfig | High |

---

## 📋 Phase 9: SSL/TLS Auditing

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Full SSL/TLS audit | `testssl.sh` | High |
| [ ] | Weak protocols (SSLv2, SSLv3, TLSv1.0) | `testssl.sh` | Critical |
| [ ] | Weak ciphers (RC4, DES, 3DES, NULL) | `testssl.sh` | Critical |
| [ ] | Certificate validity check | `testssl.sh` | High |
| [ ] | Heartbleed (CVE-2014-0160) | `testssl.sh` | Critical |
| [ ] | POODLE (CVE-2014-3566) | `testssl.sh` | High |
| [ ] | BEAST | `testssl.sh` | Medium |
| [ ] | Logjam (Weak DH) | `testssl.sh` | High |
| [ ] | Sweet32 | `testssl.sh` | Medium |
| [ ] | sslyze scan | `sslyze --regular` | High |

---

## 📋 Phase 10: Default Credentials Check

| Device / Service | Default Creds | Severity |
|-----------------|---------------|----------|
| [ ] Cisco | `admin:cisco`, `cisco:cisco` | Critical |
| [ ] Linksys | `admin:admin` | Critical |
| [ ] D-Link | `admin:<blank>` | Critical |
| [ ] Juniper | `root:<blank>` | Critical |
| [ ] HP/Aruba | `admin:admin` | Critical |
| [ ] Fortinet | `admin:<blank>` | Critical |
| [ ] MikroTik | `admin:<blank>` | Critical |
| [ ] Tomcat | `tomcat:tomcat` | Critical |
| [ ] Jenkins | `admin:admin` | Critical |
| [ ] SNMP | `public` / `private` | Critical |
| [ ] Use Hydra/Medusa/Metasploit for mass testing | — | High |

---

## 📋 Phase 11: Firewall & IDS/IPS Evasion

> 🎯 **Goal:** When standard scans fail, evade and enumerate.

| # | Technique | Command | Severity |
|---|-----------|---------|----------|
| [ ] | Packet Fragmentation (8-byte) | `nmap -f` | Medium |
| [ ] | Packet Fragmentation (16-byte) | `nmap -ff` | Medium |
| [ ] | Custom MTU | `nmap --mtu 24` | Medium |
| [ ] | Decoy Scan (10 random) | `nmap -D RND:10` | Medium |
| [ ] | Decoy Scan (specific) | `nmap -D IP1,IP2,ME` | Medium |
| [ ] | Paranoid timing | `nmap -T0` | Low |
| [ ] | Sneaky timing | `nmap -T1` | Low |
| [ ] | Scan delay | `nmap --scan-delay 5s` | Low |
| [ ] | Max rate limiting | `nmap --max-rate 10` | Low |
| [ ] | Source port spoof (DNS) | `nmap --source-port 53` | Medium |
| [ ] | Source port spoof (HTTP) | `nmap -g 80` | Medium |
| [ ] | Idle/Zombie scan | `nmap -sI <zombie>` | High |
| [ ] | Append random data | `nmap --data-length 25` | Medium |
| [ ] | FIN scan | `nmap -sF` | Medium |
| [ ] | XMAS scan | `nmap -sX` | Medium |
| [ ] | NULL scan | `nmap -sN` | Medium |
| [ ] | **Advanced:** SYN with data payload | `hping3 -S -d 100` | High |
| [ ] | **Advanced:** TCP ACK tunneling | `hping3 -A` | High |
| [ ] | **Advanced:** ICMP tunneling | `ping -p deadbeef` | High |
| [ ] | **Advanced:** HTTP tunneling | Custom | High |
| [ ] | **Advanced:** DNS tunneling | `dnscat2` | High |

---

## 📋 Phase 12: Layer 2 Switch Security

> 🎯 **Goal:** Internal network pivoting and segmentation bypass.
> 🔥 **Critical for internal pentests.**

| # | Attack | Command / Tool | Severity |
|---|--------|---------------|----------|
| [ ] | VLAN Hopping (Double Tagging) | `yersinia -I` → 802.1Q | Critical |
| [ ] | Switch Spoofing (DTP abuse) | `yersinia dtp -attack 1` | Critical |
| [ ] | Native VLAN mismatch exploit | Manual | High |
| [ ] | Private VLAN bypass | Manual | High |
| [ ] | **STP** Root Bridge Hijacking | `yersinia stp -attack 1` | Critical |
| [ ] | **STP** BPDU flooding | `yersinia` | High |
| [ ] | **STP** BPDU Guard check | `show spanning-tree` | Medium |
| [ ] | **STP** Root Guard check | `show spanning-tree` | Medium |
| [ ] | **MAC Flooding** (CAM overflow) | `macof -i eth0 -n 100000` | Critical |
| [ ] | **MAC Flooding** Switch becomes hub | Verify traffic capture | Critical |
| [ ] | MAC spoofing / cloning | `macchanger -m <MAC>` | Medium |
| [ ] | Port security bypass | MAC flood → sniff | High |
| [ ] | Sticky MAC learning bypass | Manual | Medium |
| [ ] | Dynamic ARP Inspection (DAI) bypass | `show ip arp inspection` | High |

---

## 📋 Phase 13: Network Protocol Attacks

> 🎯 **Goal:** Capture credentials and manipulate traffic on the wire.

| # | Attack | Tool | Severity |
|---|--------|------|----------|
| [ ] | LLMNR poisoning | `responder -I eth0 -rdwv` | Critical |
| [ ] | NBT-NS poisoning | `responder -I eth0 -wrfv` | Critical |
| [ ] | mDNS / Bonjour enumeration | `avahi-browse -a` | Medium |
| [ ] | WPAD hijacking | `responder -I eth0 -wpad` | Critical |
| [ ] | NetBIOS name spoofing | `nbtscan -r` | Medium |
| [ ] | Check if protocols disabled (GPO) | Manual | High |
| [ ] | Document captured hashes | Responder logs | Critical |
| [ ] | Test hash relay opportunities | `ntlmrelayx` | Critical |

---

## 📋 Phase 14: DHCP Security

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | DHCP starvation | `yersinia dhcp -attack 1` | High |
| [ ] | Rogue DHCP server detection | `nmap --script broadcast-dhcp-discover` | High |
| [ ] | DHCP snooping bypass | `show ip dhcp snooping` | High |
| [ ] | DHCP relay misconfiguration | Manual | Medium |
| [ ] | DNS server manipulation via DHCP | Manual | High |
| [ ] | Unauthorized DHCP server check | Wireshark | High |

---

## 📋 Phase 15: ARP Security

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | ARP spoofing | `arpspoof -i eth0 -t <target> <gateway>` | Critical |
| [ ] | DAI (Dynamic ARP Inspection) bypass | `show ip arp inspection` | High |
| [ ] | Gratuitous ARP flooding | `arping -U -I eth0` | Medium |
| [ ] | ARP cache poisoning | Manual | High |
| [ ] | Proxy ARP misconfiguration | `show ip interface` | Medium |

---

## 📋 Phase 16: Routing Protocol Security

| # | Protocol | Task | Severity |
|---|----------|------|----------|
| [ ] | **OSPF** | Authentication check (plaintext vs MD5) | High |
| [ ] | **OSPF** | Neighbor enumeration | `nmap --script=ospf` | Medium |
| [ ] | **OSPF** | Route injection test | Manual | Critical |
| [ ] | **BGP** | Session enumeration | `nmap --script=bgp` | Medium |
| [ ] | **BGP** | Route hijacking test | Manual | Critical |
| [ ] | **BGP** | MD5 authentication verify | Manual | High |
| [ ] | **EIGRP** | Enumeration | `nmap --script=eigrp` | Medium |
| [ ] | **EIGRP** | Route injection | Manual | Critical |
| [ ] | **VRRP** | Hijacking check | `vrrp-scanner` | High |
| [ ] | **HSRP** | Hijacking check | `yersinia hsrp -attack 1` | High |
| [ ] | **RIP** | Authentication bypass | `nmap --script=rip` | High |
| [ ] | **RIP** | Route injection | Manual | Critical |

---

## 📋 Phase 17: MPLS & VRF Testing

> 🎯 **Goal:** Service Provider and large enterprise blind spots.

| # | Task | Severity |
|---|------|----------|
| [ ] | MPLS label enumeration | Medium |
| [ ] | MPLS VPNv4 route injection test | Critical |
| [ ] | VRF route leakage test | Critical |
| [ ] | MPLS label spoofing | High |
| [ ] | VRF-aware NAT misconfiguration | Medium |
| [ ] | MPLS L3VPN isolation verification | Critical |
| [ ] | MPLS TE tunnel hijacking | High |

---

## 📋 Phase 18: Multicast Security

| # | Task | Severity |
|---|------|----------|
| [ ] | IGMP snooping bypass | High |
| [ ] | PIM enumeration | `nmap --script=pim` | Medium |
| [ ] | MSDP check (port 639) | Medium |
| [ ] | IGMP version vulnerability (v1/v2) | Medium |
| [ ] | Multicast group membership hijacking | High |
| [ ] | Multicast boundary / scope misconfig | Medium |
| [ ] | ASM vs SSM security check | Low |

---

## 📋 Phase 19: IPv6 Network Testing

| # | Task | Command | Severity |
|---|------|---------|----------|
| [ ] | Link-local discovery | `nmap -6 -sn fe80::/10` | Info |
| [ ] | Multicast ping (all nodes) | `ping6 -c 4 ff02::1%eth0` | Info |
| [ ] | Full IPv6 port scan | `nmap -6 -Pn -p- -sV` | Info |
| [ ] | THC-IPv6 alive discovery | `atk6-alive6 eth0` | Info |
| [ ] | Router discovery | `atk6-dump_router6 eth0` | Medium |
| [ ] | **ICMPv6 Router Advertisement Spoofing** | `atk6-fake_router6` | Critical |
| [ ] | **NDP Spoofing** (IPv6 ARP) | `atk6-parasite6 eth0` | Critical |
| [ ] | **SLAAC Attack** | Manual | High |
| [ ] | **DHCPv6 Starvation** | `atk6-flood_dhcpc6 eth0` | High |
| [ ] | Dual-stack misconfiguration check | Manual | High |
| [ ] | IPv6 tunnel interfaces (6to4, Teredo, ISATAP) | `ip -6 tunnel show` | Medium |
| [ ] | Firewall IPv4 vs IPv6 rule parity | Manual | Critical |

---

## 📋 Phase 20: Network Segmentation Validation

> 🎯 **Goal:** Verify if segmentation actually works or is just "paper security."
> 🆕 **New addition — often missed by automated scanners.**

| # | Task | Severity |
|---|------|----------|
| [ ] | East-West traffic inspection (can VLANs talk?) | Critical |
| [ ] | Inter-VLAN routing ACL validation | Critical |
| [ ] | DMZ → Internal network jump test | Critical |
| [ ] | Guest network → Corporate network test | Critical |
| [ ] | PCI zone isolation verification | Critical |
| [ ] | SCADA/OT network segmentation test | Critical |
| [ ] | Micro-segmentation bypass (if SDN deployed) | High |
| [ ] | Zero Trust policy validation | High |
| [ ] | SD-WAN overlay security test | High |
| [ ] | SASE (Secure Access Service Edge) policy bypass | High |
| [ ] | Container network namespace isolation | Medium |
| [ ] | Cloud VPC/VNet peering security | High |

---

## 📋 Phase 21: NDR Evasion & Stealth

> 🎯 **Goal:** Evade Network Detection & Response (NDR) solutions.
> 🆕 **New addition — modern networks have Darktrace, Vectra, ExtraHop, etc.**

| # | Technique | Severity |
|---|-----------|----------|
| [ ] | Slow & low scan (below NDR threshold) | Medium |
| [ ] | Legitimate user agent spoofing | Low |
| [ ] | Domain Fronting (if HTTP egress allowed) | High |
| [ ] | JA3/JA3S TLS fingerprint randomization | Medium |
| [ ] | Beacon jitter (irregular C2 intervals) | High |
| [ ] | Protocol-abuse (DNS over HTTPS, QUIC) | High |
| [ ] | Living-off-the-land (LOLbins) for lateral movement | High |
| [ ] | Encrypted C2 channels (HTTPS, DNSSEC, DoH) | High |
| [ ] | NDR baseline behavior analysis (learn then evade) | Critical |
| [ ] | Network flow (NetFlow/sFlow) evasion | Medium |
| [ ] | SIEM log noise generation (cover tracks) | High |

---

## 📋 Phase 22: Password Attacks & Hash Cracking

### Online Brute Force

| # | Service | Tool | Severity |
|---|---------|------|----------|
| [ ] | SSH | `hydra -l admin -P rockyou.txt ssh://target` | High |
| [ ] | FTP | `hydra -L users.txt -P pass.txt ftp://target` | High |
| [ ] | RDP | `hydra -l administrator -P rockyou.txt rdp://target` | High |
| [ ] | HTTP Basic Auth | `hydra -l admin -P pass.txt http-get://target` | High |
| [ ] | SMB | `hydra -l administrator -P pass.txt smb://target` | High |
| [ ] | Telnet | `hydra -l admin -P pass.txt telnet://target` | High |
| [ ] | VNC | `hydra -P pass.txt vnc://target` | High |
| [ ] | Medusa parallel brute | `medusa -h target -u admin -P rockyou.txt -M ssh` | High |
| [ ] | Metasploit login scanners | `auxiliary/scanner/*/*_login` | High |

### Offline Hash Cracking

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Dump SAM hashes | `hashdump` (Meterpreter) | Critical |
| [ ] | Mimikatz credential dump | `sekurlsa::logonpasswords` | Critical |
| [ ] | Linux shadow cracking | `unshadow` + `john` | High |
| [ ] | NTLM cracking | `hashcat -m 1000` | High |
| [ ] | NTLMv2 cracking | `hashcat -m 5600` | High |
| [ ] | Kerberoast TGS cracking | `hashcat -m 13100` | High |
| [ ] | AS-REP Roast cracking | `hashcat -m 18200` | High |
| [ ] | Rules-based attack | `hashcat -r best64.rule` | High |

### Advanced Credential Attacks

| # | Attack | Tool | Severity |
|---|--------|------|----------|
| [ ] | Pass-the-Hash (PTH) | `crackmapexec smb -H` | Critical |
| [ ] | NTLM Relay | `impacket-ntlmrelayx` | Critical |
| [ ] | Responder hash capture | `responder -I eth0 -rdwv` | Critical |

---

## 📋 Phase 23: Active Directory Testing

### Initial Enumeration

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Domain identification | `systeminfo`, `net user /domain` | Info |
| [ ] | LDAP enumeration | `ldapsearch` | Medium |
| [ ] | enum4linux-ng | `enum4linux-ng -A` | Medium |

### Attack Path Mapping

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | BloodHound data collection | `bloodhound-python` | High |
| [ ] | Shortest path to Domain Admin | BloodHound GUI | Critical |
| [ ] | Kerberoastable users | BloodHound | High |
| [ ] | AS-REP Roastable users | BloodHound | High |

### Kerberos Attacks

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Kerberoasting | `impacket-GetUserSPNs` | High |
| [ ] | AS-REP Roasting | `impacket-GetNPUsers` | High |
| [ ] | DCSync (Domain Admin) | `impacket-secretsdump` | Critical |

### AD Assessment Tools

| # | Tool | Purpose | Severity |
|---|------|---------|----------|
| [ ] | **linWinPwn** | All-in-one AD enum from Linux | High |
| [ ] | **PingCastle** | AD health/risk score | High |
| [ ] | **ADRecon** | Detailed AD info (GPOs, ACLs) | Medium |
| [ ] | **adidnsdump** | ALL internal DNS records | High |
| [ ] | **Snaffler** | Credentials in SMB shares | High |
| [ ] | **scavenger** | Sensitive data discovery | Medium |

### Lateral Movement

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | PsExec | Metasploit `psexec` | High |
| [ ] | WMI execution | `crackmapexec wmi` | High |
| [ ] | WinRM shell | `evil-winrm` | High |

### ✅ AD Checklist Summary
- [ ] Identify domain, DC IP, functional level
- [ ] Run linWinPwn for comprehensive enum
- [ ] Run PingCastle for risk scoring
- [ ] Run BloodHound for attack path mapping
- [ ] Run ADRecon for detailed inventory
- [ ] Run adidnsdump for hidden DNS records
- [ ] Kerberoast all SPN accounts
- [ ] AS-REP Roast no-preauth accounts
- [ ] Check ACL misconfigurations (GenericAll, WriteDACL)
- [ ] Check weak password policy
- [ ] Test SMB signing → NTLM Relay
- [ ] Run Snaffler for credential hunting
- [ ] Attempt DCSync if Domain Admin achieved

---

## 📋 Phase 24: Exploitation & Post-Exploitation

> ✅ **Only perform if explicitly authorized in scope.**

### Remote Access

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Remote hash dumping | `impacket-secretsdump` | Critical |
| [ ] | WinRM shell access | `evil-winrm` | High |
| [ ] | PsExec remote execution | Metasploit `psexec` | High |

### Post-Exploitation Discovery

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Full system recon | `Seatbelt.exe -group=all` | High |
| [ ] | Password extraction from apps | `laZagne.exe all` | Critical |
| [ ] | Stealthy LSASS dump | `nanodump.exe` | Critical |
| [ ] | Remote DPAPI looting | `dploot` | High |
| [ ] | Network credential capture | `PCredz` | High |

### Tunneling & Pivoting

| # | Task | Tool | Severity |
|---|------|------|----------|
| [ ] | Reverse TUN tunnel | `ligolo-ng` | High |
| [ ] | DNS tunneling C2 | `dnscat2` | High |
| [ ] | ICMP tunneling | `icmpsh`, `ptunnel` | High |
| [ ] | SSH port forwarding | `ssh -L / -D` | Medium |
| [ ] | GRE tunnel enumeration | Manual | Medium |
| [ ] | IP-in-IP tunneling | Manual | Medium |

### ✅ Post-Exploitation Summary
- [ ] Dump credentials (secretsdump, nanodump, LaZagne)
- [ ] Access WinRM shell (evil-winrm)
- [ ] Run Seatbelt for system intel
- [ ] DPAPI looting with dploot
- [ ] Passive credential capture with PCredz
- [ ] Set up ligolo-ng for internal pivoting
- [ ] Test covert channels (ICMP, DNS, HTTP tunneling)
- [ ] **CLEAN UP ALL ARTIFACTS** (shells, uploads, scripts)
- [ ] Verify no persistence left behind

---

## 📋 Phase 25: Reporting

| # | Section | Priority |
|---|---------|----------|
| [ ] | Executive Summary (non-technical, business impact) | Critical |
| [ ] | Scope and Methodology | Critical |
| [ ] | Vulnerability table (CVE, CVSS v3.1, Severity) | Critical |
| [ ] | Detailed findings per vulnerability | Critical |
| [ ] | Evidence (screenshots, command output, PCAP) | Critical |
| [ ] | Risk / Impact analysis | High |
| [ ] | Remediation recommendations (prioritized) | Critical |
| [ ] | Appendix: Raw tool outputs (Nmap, Nessus, etc.) | Medium |
| [ ] | Risk rating matrix | High |
| [ ] | Retest guidance after remediation | High |
| [ ] | Compliance mapping (PCI-DSS, ISO 27001, NIST) | Medium |

---

## 🛠️ Tools Reference

### Reconnaissance & OSINT
| Tool | Purpose |
|------|---------|
| Nmap | Port scanning, service & OS detection |
| masscan | Ultra-fast port scanning |
| SpiderFoot | Automated OSINT (200+ sources) |
| reconftw | Full-chain automated recon |
| dnsrecon | DNS enumeration + AXFR |
| AORT | All-in-One Recon Tool |
| Shodan | Internet-facing system discovery |
| skanuvaty | Fast DNS/network/port scanner |
| Dismap | Asset discovery & fingerprinting |
| Metabigor | ASN/IP range discovery (no API) |
| Gobuster | DNS subdomain brute force |
| smtp-user-enum | SMTP user enumeration |
| Hping3 | Custom packet crafting |
| netdiscover | Passive ARP recon |
| lbd | Load balancer detector |
| p0f | Passive OS fingerprinting |

### Vulnerability Scanning
| Tool | Purpose |
|------|---------|
| Nessus | Automated vulnerability scanning |
| OpenVAS | Open source vulnerability scanner |
| Nuclei | Fast template-based scanner |
| Nikto | Web server scanner |

### SSL/TLS Auditing
| Tool | Purpose |
|------|---------|
| testssl.sh | Full SSL/TLS audit |
| sslyze | SSL/TLS scanner |

### Credential Attacks
| Tool | Purpose |
|------|---------|
| Hydra | Multi-protocol brute force |
| Medusa | Parallel brute forcing |
| Hashcat | GPU-accelerated hash cracking |
| John the Ripper | Password/hash cracking |
| Responder | NTLM hash capture (LLMNR/NBT-NS) |
| Mimikatz | Windows credential dumping |
| LaZagne | Extract passwords from local apps |
| nanodump | Stealthy LSASS minidump |
| dploot | Remote DPAPI looting |
| PCredz | Credential capture from PCAP/live traffic |

### Active Directory
| Tool | Purpose |
|------|---------|
| BloodHound | AD attack path visualization |
| Impacket | Windows protocol attack suite |
| CrackMapExec | AD/SMB lateral movement |
| Evil-WinRM | WinRM shell |
| Kerbrute | Kerberos user enum & brute force |
| Rubeus | Kerberoast, AS-REP roast, ticket attacks |
| linWinPwn | All-in-one AD enum from Linux |
| PingCastle | AD risk assessment |
| ADRecon | Detailed AD info (GPOs, ACLs) |
| adidnsdump | Dump all DNS records from AD |
| Snaffler | Find credentials in SMB shares |
| Coercer | Force Windows server to authenticate |

### Lateral Movement & Post-Exploitation
| Tool | Purpose |
|------|---------|
| Metasploit | Exploitation framework |
| PsExec | Remote execution via SMB |
| ligolo-ng | Reverse tunnel with TUN interface |
| Seatbelt | Local system recon |
| scavenger | Sensitive data discovery |
| Dnscat2 | C2 via DNS tunneling |
| icmpsh | ICMP tunneling shell |
| ptunnel | ICMP tunneling |

### Network Analysis & Layer 2/3
| Tool | Purpose |
|------|---------|
| Wireshark | Packet capture/analysis |
| Burp Suite | Web proxy / app testing |
| enum4linux | SMB/NetBIOS/AD enumeration |
| snmpwalk | SNMP enumeration |
| THC-IPv6 | IPv6 attack toolkit |
| yersinia | Network protocol attacks (STP, DHCP, 802.1Q) |
| macof | MAC flooding (CAM overflow) |
| macchanger | MAC address spoofing |
| arpspoof | ARP spoofing |
| arping | ARP ping / gratuitous ARP |
| dhcpstarv | DHCP starvation |
| ike-scan | IPSec VPN enumeration |
| sipvicious | SIP/VoIP testing suite |
| vrrp-scanner | VRRP protocol scanner |
| stpscan | STP scanner |

### Platforms
| Tool | Purpose |
|------|---------|
| Kali Linux | Pentest OS |
| Parrot OS | Alternative pentest OS |

---

## ⚡ One-Liners Cheat Sheet

```bash
# === RECON ===
whois <domain> && dig ANY <domain> && dnsrecon -d <domain>

# === HOST DISCOVERY ===
nmap -sn 192.168.1.0/24 && arp-scan --localnet

# === FULL PORT SCAN ===
nmap -Pn -p- -sS -sV -T4 <target> -oN full_tcp.txt
masscan -p1-65535 <target> --rate=10000 -oG masscan.gnmap

# === SERVICE ENUM ===
nmap -Pn -sC -sV -p <ports> <target>
nmap -Pn -p80,443 --script=http-methods,http-title,ssl-enum-ciphers <target>

# === VULN SCAN ===
nuclei -target <target> -severity critical,high
nikto -h http://<target>

# === SSL/TLS ===
./testssl.sh <target>:443
sslyze --regular <target>:443

# === CREDENTIALS ===
hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://<target>
onesixtyone -c dict.txt <target>          # SNMP
smbclient -L //<target>/ -N               # SMB null session

# === LAYER 2 ===
macof -i eth0 -n 100000                   # MAC flood
yersinia -I                               # STP/DHCP/VLAN attacks
arpspoof -i eth0 -t <target> <gateway>    # ARP spoof

# === NETWORK PROTOCOLS ===
responder -I eth0 -rdwv                     # LLMNR/NBT-NS/WPAD

# === AD ===
enum4linux-ng -A <dc-ip>
bloodhound-python -u <user> -p <pass> -d <domain> -ns <dc-ip> -c all
impacket-GetUserSPNs <domain>/<user>:<pass> -dc-ip <dc-ip> -request

# === POST-EXPLOITATION ===
impacket-secretsdump <domain>/<user>:<pass>@<target>
evil-winrm -i <target> -u administrator -p <password>
./proxy -selfcert -laddr 0.0.0.0:11601    # ligolo-ng
```

---

## 📊 Severity Classification

| Severity | CVSS v3.1 | Description | Example |
|----------|-----------|-------------|---------|
| **Critical** | 9.0–10.0 | Immediate exploitation, full compromise | EternalBlue, BlueKeep, default creds |
| **High** | 7.0–8.9 | Significant impact, easy to exploit | SMB signing disabled, NTLM relay, ARP spoof |
| **Medium** | 4.0–6.9 | Moderate impact, requires some conditions | Weak ciphers, info disclosure, VLAN hopping |
| **Low** | 0.1–3.9 | Minor impact, hard to exploit | Banner disclosure, outdated software |
| **Info** | 0.0 | Informational only | OS fingerprint, service version |

---

## 🏛️ Compliance Mapping

| Checklist Phase | PCI-DSS | ISO 27001 | NIST CSF | HIPAA |
|-----------------|---------|-----------|----------|-------|
| Pre-Engagement | 12.3 | A.12.1.1 | ID.RA | 164.308(a)(8) |
| Reconnaissance | 11.3.2 | A.12.6.1 | DE.CM | 164.308(a)(1) |
| Vulnerability Scanning | 11.3.2 | A.12.6.1 | DE.CM | 164.308(a)(8) |
| SSL/TLS Auditing | 4.1, 4.2 | A.10.1.1 | PR.DS | 164.312(a)(2)(iv) |
| Default Credentials | 2.1 | A.9.2.1 | PR.AC | 164.308(a)(4) |
| Firewall Evasion | 1.2, 1.3 | A.10.1.2 | PR.AC | 164.308(a)(3) |
| Layer 2 Security | 1.2, 1.3 | A.10.1.2 | PR.AC | 164.308(a)(3) |
| AD Testing | 8.2 | A.9.2.1 | PR.AC | 164.308(a)(4) |
| Segmentation Validation | 1.3 | A.10.1.2 | PR.AC | 164.308(a)(3) |
| Reporting | 11.3.4 | A.12.6.1 | ID.RA | 164.308(a)(8) |

---

## 📁 Repo Structure

```
network-vapt-checklist/
├── README.md                          ← This file
├── CHECKLIST.md                       ← Printable version (no commands)
├── reports/
│   ├── executive_summary_template.md
│   ├── technical_findings_template.md
│   └── sample_report.pdf
├── scripts/
│   ├── nmap_full_scan.sh
│   ├── masscan_wrapper.sh
│   └── auto_nuclei.sh
├── screenshots/                       ← Evidence folder (gitignored)
├── wordlists/
│   ├── custom_subdomains.txt
│   └── network_devices_creds.txt
├── .github/
│   └── CONTRIBUTING.md
└── LICENSE
```

---

## 🤝 Contributing

We welcome contributions from the security community!

### How to Contribute
1. **Fork** this repository
2. **Create a branch** (`git checkout -b feature/new-attack-vector`)
3. **Add your contribution** (new test case, tool, or command)
4. **Test** your additions for accuracy
5. **Submit a Pull Request** with clear description

### Contribution Guidelines
- Ensure all tests are for **authorized security assessments only**
- Include severity classification for new findings
- Provide tool installation commands if introducing new tools
- Update the Tools Reference table for any new additions
- Follow the existing markdown formatting style

### Code of Conduct
- This project follows responsible disclosure practices
- Do not submit zero-day exploits without proper coordination
- Respect all applicable laws and regulations

---

## 📄 License

```
MIT License

Copyright (c) 2026 Network VAPT Checklist Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.

---

⚠️ IMPORTANT: This checklist is for AUTHORIZED security testing only.
Unauthorized access to computer systems is illegal.
The authors assume no liability for misuse.
```

---

> **Made with ❤️ for the security community**
>
> *"The best defense is a good offense — but only when authorized."*
>
> **Always hack ethically. 🛡️**
