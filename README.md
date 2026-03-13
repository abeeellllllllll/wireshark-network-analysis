# Wireshark Network Traffic Analysis

A hands-on network traffic analysis project using Wireshark to capture and inspect live packets on a home lab environment. This project demonstrates practical knowledge of core networking protocols and basic security analysis concepts.

---

## Tools Used

- **Wireshark** — packet capture and protocol analysis
- **Kali Linux** (VirtualBox) — capture environment
- **Protocols Analysed** — DNS, HTTP, ICMP, TCP

---

## Project Overview

Live network traffic was captured on a Kali Linux machine running in VirtualBox. The capture was filtered and analysed across four key protocols to understand how data flows across a network and identify potential security concerns.

| Protocol | Purpose | Key Finding |
|----------|---------|-------------|
| DNS | Domain name resolution | Queries to 8.8.8.8 resolved domains in plaintext — names visible to any observer on the network |
| HTTP | Unencrypted web traffic | Full request and response headers readable in plaintext via TCP stream follow — credentials and content exposed |
| ICMP | Network connectivity testing | Ping echo requests and replies confirmed host reachability and measured round-trip latency |
| TCP | Transport-layer connections | Three-way handshake (SYN → SYN-ACK → ACK) observed and confirmed reliable connection establishment |

---

## Key Security Findings

- **HTTP exposes data in plaintext** — using the "Follow TCP Stream" feature, the full contents of HTTP sessions were readable without any decryption. The same traffic over HTTPS would be unreadable.
- **DNS queries are unencrypted by default** — every domain lookup is visible to anyone monitoring the network, enabling tracking of browsing behaviour.
-  **Port scan traffic detected in real time** — Nmap scan activity 
  generated a flood of TCP SYN packets to sequential ports, 
  visible live in Wireshark — demonstrating passive intrusion 
  detection capability.

---

## Report

The full written analysis including annotated screenshots, protocol breakdowns, and security recommendations is available here:

📄 **[View Full Report (PDF)](report/Wireshark_report.pdf)**

---

## Repository Structure

```
wireshark-network-analysis/
├── README.md
├── report/
│   └── wireshark_analysis_report.pdf
├── captures/
│   └── capture.pcap
└── screenshots/
    ├── live_capture.png
    ├── DNS_filter.png
    ├── ICMP_filter.png
    ├── HTTP_filter.png
    ├── TCP_stream.png
    └── TCP_filter.png
```

---

## Skills Demonstrated

`Wireshark` `Packet Analysis` `TCP/IP` `Protocol Inspection` `DNS` `HTTP` `ICMP` `Network Security` `Linux` `Security Documentation`
