# CampusLab

**Design, build, secure and attack a redundant corporate campus network — end to end.**

CampusLab is a hands-on networking and security lab. It models the network of a small company with **two buildings and a small data center**, built step by step following the **hierarchical network design model** (access / distribution / core), then hardened and finally attacked and defended from inside the lab.

Every phase includes the Packet Tracer / GNS3 files, the device configurations, a design document explaining *why* each decision was taken, and verification evidence.

> ⚠️ **Lab-only disclaimer.** All offensive techniques in this repository are executed exclusively inside an isolated virtual lab that I own. Nothing here is intended or authorised for use against networks or systems belonging to others.

---

## Goals

- Apply the hierarchical model, Switching Blocks and collapsed core to a realistic scenario.
- Provide high availability and load sharing (HSRP, PVST, EtherChannel/LACP, redundant DHCP).
- Run IPv4/IPv6 dual-stack with a hierarchical addressing plan.
- Carry VoIP with QoS and measure call quality (jitter, packet loss, MOS).
- Segment the network securely (inter-VLAN ACLs, edge firewall, VPN).
- Reproduce common Layer 2/3 attacks and validate the corresponding defences.
- Build small Python tools to calculate, monitor and verify the network.

## Roadmap

| Phase | Topic | Key technologies | Status |
|---|---|---|---|
| 1 | [Switching Block](phases/01-switching-block/) | VLANs, 802.1Q trunks, port security, addressing plan | 🔄 In progress |
| 2 | [High availability & load sharing](phases/02-high-availability/) | HSRP (+preempt), redundant DHCP, PVST+, EtherChannel (LACP), collapsed core | ⏳ Planned |
| 3 | [IPv6 dual-stack](phases/03-ipv6-dual-stack/) | Hierarchical IPv6 plan, SLAAC/EUI-64, IPv6 routing | ⏳ Planned |
| 4 | [VoIP with QoS](phases/04-voip-qos/) | FreePBX, voice VLAN, CoS/QoS, jitter / loss / MOS measurement | ⏳ Planned |
| 5 | [Secure design](phases/05-secure-design/) | Inter-VLAN ACLs, pfSense/OPNsense edge firewall, NAT, WireGuard VPN, SSH | ⏳ Planned |
| 6 | [Detection](phases/06-detection/) *(optional)* | Suricata IDS, centralised logging | ⏳ Planned |
| 7 | [Attack & defence](phases/07-attack-defense/) | MAC flooding, STP root attack, HSRP hijack, rogue DHCP, ARP spoofing, VLAN hopping | ⏳ Planned |
| — | [Python tools](tools/) | Bandwidth & subnet calculators, RTT/jitter monitor, failover tester | ⏳ Planned |

## Repository structure

```
campuslab/
├── README.md                 ← you are here
├── docs/
│   └── diagrams/             ← topology diagrams (PNG/drawio)
├── phases/
│   ├── 01-switching-block/
│   │   ├── README.md         ← design decisions, how to verify, lessons learned
│   │   ├── configs/          ← running-config of every device
│   │   └── *.pkt             ← Packet Tracer file
│   ├── 02-high-availability/
│   └── ...
└── tools/                    ← Python utilities
```

## Tools

- Cisco Packet Tracer (phases 1–3)
- GNS3 / EVE-NG, pfSense/OPNsense, Kali Linux (phases 5–7)
- FreePBX / Asterisk, Wireshark, sngrep, `tc netem` (phase 4)
- Python 3 + Tkinter (tools)

## Author

**Mario Antonio Casasola Stokes** — Telecommunications Engineering student, Universidad de Granada.
