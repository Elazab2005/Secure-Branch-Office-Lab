&#x20;# Secure Branch Office Network Lab



\## 📌 Scenario

A small medical clinic network divided into:

\- \*\*VLAN 10 (Staff)\*\* - Can access Medical Records

\- \*\*VLAN 20 (Guest)\*\* - Internet only, no access to sensitive data

\- \*\*VLAN 30 (Management)\*\* - Secure remote management via SSH



\## 🏗️ Topology

\- \*\*IOU1 (MLS)\*\* - Core Multilayer Switch with Inter-VLAN Routing

\- \*\*IOU2 (Access Switch)\*\* - Connects PC1 (Staff) \& PC2 (Guest)

\- \*\*IOU3 (Access Switch)\*\* - Connects PC3 (Staff) \& PC4 (Guest)

\- \*\*PC5\*\* - Management PC connected to IOU1



\## 🔧 Technologies Implemented

\- ✅ VLANs (10-Staff, 20-Guest, 30-Management)

\- ✅ EtherChannel (LACP) - Trunk aggregation between switches

\- ✅ Inter-VLAN Routing (SVIs) on Multilayer Switch

\- ✅ Port Security with sticky MAC on Management port

\- ✅ SSHv2 for secure remote access

\- ✅ ACL blocking Guest VLAN from accessing Management VLAN



\## 📊 IP Addressing



| Device | IP Address | VLAN | Gateway |

|--------|------------|------|---------|

| PC1 (Staff) | 192.168.10.10/24 | 10 | 192.168.10.1 |

| PC2 (Guest) | 192.168.20.10/24 | 20 | 192.168.20.1 |

| PC3 (Staff) | 192.168.10.11/24 | 10 | 192.168.10.1 |

| PC4 (Guest) | 192.168.20.11/24 | 20 | 192.168.20.1 |

| PC5 (Management) | 192.168.30.5/24 | 30 | 192.168.30.1 |

| IOU1 (MLS) | 192.168.30.1/24 | 30 | N/A |

| IOU2 (SW) | 192.168.30.2/24 | 30 | 192.168.30.1 |

| IOU3 (SW) | 192.168.30.3/24 | 30 | 192.168.30.1 |



\## 🔐 SSH Access



| Device | Management IP | Username | Password |

|--------|---------------|----------|----------|

| IOU1 (MLS Core) | 192.168.30.1 | Soliman | 1234 |

| IOU2 (Access SW) | 192.168.30.2 | Soliman | 1234 |

| IOU3 (Access SW) | 192.168.30.3 | Soliman | 1234 |



\### SSH Command Example:

ssh -l Soliman 192.168.30.1



