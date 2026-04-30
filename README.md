# Network Traffic Analysis using Wireshark

## Overview
This project presents a practical network traffic analysis performed using **Wireshark Packet Analyzer** on a Linux system. The goal of the project was to capture, filter, and analyze real network packets to understand common network protocols and identify normal versus potentially suspicious traffic behavior.

The analysis covers multiple protocols including **ICMP, DNS, TCP, UDP/QUIC, TLS, and HTTP**.

---

## Project Objectives
- Capture live network traffic using Wireshark
- Analyze protocol behavior using display filters
- Study ICMP echo request/reply communication
- Examine DNS resolution and NXDOMAIN responses
- Inspect TCP traffic and HTTPS communication over port 443
- Identify UDP/QUIC traffic used by modern HTTP/3 browsing
- Review encrypted TLS communication
- Document security observations and recommendations

---

## Tools & Environment
| Item | Details |
|---|---|
| Tool | Wireshark Packet Analyzer |
| Operating System | Linux |
| Interface | Wireless LAN interface |
| Capture Type | Live packet capture |
| Analysis Type | Protocol inspection and traffic filtering |

---

## Protocols Analyzed

### ICMP
ICMP traffic was analyzed to observe echo request and echo reply packets generated during ping communication. This helped confirm host reachability and basic diagnostic behavior.

### DNS
DNS queries and responses were inspected to understand how domain names are resolved into IP addresses. NXDOMAIN responses were also observed, indicating failed domain lookups.

### TCP
TCP traffic was reviewed to study established communication sessions, acknowledgment packets, and traffic over port 443 used for HTTPS communication.

### UDP / QUIC
UDP traffic was largely composed of QUIC packets, which are commonly used by HTTP/3 in modern browsers for faster encrypted communication.

### TLS
TLS traffic was analyzed to confirm encrypted communication between the host and external servers.

### HTTP
A small amount of unencrypted HTTP traffic was observed within the internal network, highlighting the importance of using HTTPS for sensitive communication.

---

## Wireshark Filters Used

```text
ip.addr == <host-ip>

ip.addr == <host-ip> and icmp
ip.addr == <host-ip> and dns
ip.addr == <host-ip> and tcp
ip.addr == <host-ip> and udp
ip.addr == <host-ip> and tls
ip.addr == <host-ip> and http
