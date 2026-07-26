# Repository Structure & Topic Progression

This document outlines the folder structure and the chronological learning order for the **Cisco IOS Comprehensive Guide**. 

The goal of this repository is to build knowledge progressively. Topics are ordered from the easiest, most fundamental concepts to the hardest, most advanced enterprise configurations. 

## 📁 Contributor Note: Where to Put Files
**Important:** Do NOT place images, Packet Tracer (`.pkt`), EVE-NG, GNS3 lab files, or configuration text files in a global root folder. 

Every topic must be entirely self-contained. When you add a new topic, create a dedicated folder for it and place your `README.md` (copied from `_template.md`), your topology images, and any lab files directly inside that specific folder.

**Example of a correct structure:**
```text
01-Device-Basics/
├── 01-CLI-Navigation/
│   ├── README.md
│   └── topology.png
├── 02-Hostname/
│   ├── README.md
│   ├── topology.png
│   └── initial_configs.txt
```

---

## 🗺️ Topic Progression (Easiest to Hardest)

To maintain organization, folders should be numbered exactly as shown below so they sort correctly in GitHub.

### `01-Device-Basics/`
* `01-CLI-Navigation`
* `02-Hostname`
* `03-User-Accounts-and-Passwords`
* `04-VTY-Telnet-SSH`
* `05-Banner-MOTD`
* `06-Saving-and-Backing-Up`
* `07-Basic-Show-Commands`
* `08-Password-Recovery`

### `02-Interface-Configuration/`
* `01-Ethernet-Interfaces`
* `02-Loopback-Interfaces`
* `03-Interface-Descriptions`
* `04-Speed-and-Duplex`
* `05-Shutdown-No-Shutdown`
* `06-Bandwidth-and-Delay`
* `07-IPv4-Addressing`
* `08-Secondary-IP-Addresses`
* `09-IPv6-Addressing`

### `03-Layer-2-Switching/`
* `01-VLAN-Creation`
* `02-Access-Ports`
* `03-Trunk-Ports-8021Q`
* `04-Native-VLAN`
* `05-Voice-VLAN`
* `06-VLAN-Pruning`
* `07-VTP`
* `08-DTP`
* `09-EtherChannel-LACP`
* `10-EtherChannel-PAgP`

### `04-Spanning-Tree/`
* `01-STP-Basics`
* `02-PVST-Plus`
* `03-Rapid-PVST-Plus`
* `04-MST`
* `05-Root-Bridge-Election`
* `06-PortFast`
* `07-BPDU-Guard`
* `08-BPDU-Filter`
* `09-Root-Guard`
* `10-Loop-Guard`
* `11-UDLD`

### `05-IP-Routing/`
* `01-Static-Routing`
* `02-Default-Route`
* `03-Floating-Static-Route`
* `04-ECMP-Load-Balancing`
* `05-IPv6-Static-Routing`

### `06-Dynamic-Routing/`
* `01-RIP`
* `02-OSPF-Single-Area`
* `03-OSPF-Multi-Area`
* `04-OSPF-Authentication`
* `05-OSPF-Summarization`
* `06-OSPF-Stub-Areas`
* `07-EIGRP`
* `08-EIGRP-Authentication`
* `09-EIGRP-Summarization`
* `10-BGP-Basic-Configuration`
* `11-BGP-Path-Attributes`
* `12-BGP-Route-Filtering`
* `13-BGP-Route-Reflector`
* `14-BGP-Confederation`

### `07-Route-Control/`
* `01-Standard-ACL`
* `02-Extended-ACL`
* `03-Named-ACL`
* `04-IPv6-ACL`
* `05-Route-Redistribution`
* `06-Administrative-Distance`
* `07-Prefix-Lists`
* `08-Route-Maps`
* `09-Policy-Based-Routing-PBR`
* `10-IP-SLA`
* `11-Object-Tracking`

### `08-NAT-Services/`
* `01-Static-NAT`
* `02-Dynamic-NAT`
* `03-PAT-NAT-Overload`
* `04-NAT-Exemption`

### `09-DHCP-and-Address-Services/`
* `01-DHCP-Server`
* `02-DHCP-Relay`
* `03-DHCP-Snooping`
* `04-IPv6-DHCP`
* `05-DNS-Configuration`

### `10-High-Availability/`
* `01-HSRP`
* `02-VRRP`
* `03-GLBP`

### `11-First-Hop-and-Multicast/`
* `01-IGMP`
* `02-PIM`
* `03-Multicast-Routing`

### `12-QoS/`
* `01-QoS-Classification`
* `02-QoS-Marking`
* `03-Policing`
* `04-Shaping`
* `05-CBWFQ`
* `06-LLQ`
* `07-WRED`

### `13-Security/`
* `01-Port-Security`
* `02-Storm-Control`
* `03-Dynamic-ARP-Inspection`
* `04-IP-Source-Guard`
* `05-Device-Hardening`
* `06-SSH-Configuration`
* `07-AAA-Local-Authentication`
* `08-RADIUS-Authentication`
* `09-TACACS-Plus`
* `10-Control-Plane-Policing-CoPP`

### `14-Infrastructure-Services/`
* `01-NTP`
* `02-Syslog`
* `03-SNMP`
* `04-NetFlow`
* `05-SPAN-RSPAN`
* `06-Embedded-Packet-Capture`
* `07-Archive-Configuration`

### `15-Virtualization/`
* `01-VRF-Lite`
* `02-GRE-Tunnel`
* `03-GRE-over-IPSec`
* `04-IPSec-Site-to-Site-VPN`
* `05-DMVPN`
* `06-MPLS-L3VPN`

### `16-IPv6/`
* `01-IPv6-Routing-Basics`
* `02-OSPFv3`
* `03-EIGRP-for-IPv6`
* `04-IPv6-FHRP`

### `17-WAN/`
* `01-Serial-Links`
* `02-HDLC`
* `03-PPP`
* `04-PPP-Authentication-PAP-CHAP`
* `05-Metro-Ethernet-Overview`

### `18-Automation/`
* `01-Embedded-Event-Manager-EEM`
* `02-NETCONF`
* `03-RESTCONF`
* `04-Model-Driven-Telemetry`
* `05-Cisco-IOS-API-Basics`

### `19-Monitoring-and-Troubleshooting/`
* `01-CDP`
* `02-LLDP`
* `03-Ping-and-Extended-Ping`
* `04-Traceroute`
* `05-Debug-Commands`
* `06-Conditional-Debug`
* `07-Logging-Analysis`

### `20-Enterprise-Labs/`
* `01-Branch-Office-Network`
* `02-Inter-VLAN-Enterprise-Campus`
* `03-Multi-Area-OSPF-Network`
* `04-Dual-ISP-with-BGP`
* `05-Redundant-Campus-Network`
* `06-Secure-Enterprise-Edge`
* `07-QoS-for-Voice-Network`
* `08-DMVPN-Hub-and-Spoke`
* `09-IPSec-Site-to-Site-Enterprise`
* `10-Complete-Enterprise-Network`
