# Wireshark Packet Analysis Lab

## Overview

This project demonstrates hands-on experience with **Wireshark packet capture and network traffic analysis** in an isolated virtual lab environment.

The lab focuses on identifying and analyzing common network protocols, examining packet details, applying Wireshark display filters, and documenting network communication between virtual machines.

## Objectives

* Capture live network traffic using Wireshark
* Analyze Ethernet and IP packet information
* Identify and analyze ICMP traffic
* Analyze DNS queries and responses
* Examine TCP communication and connection establishment
* Identify TCP three-way handshakes
* Analyze HTTP requests and responses
* Use Wireshark display filters to isolate network traffic
* Use packet details and TCP stream analysis to investigate communications
* Document findings and observations

## Lab Environment

| Component        | Details                      |
| ---------------- | ---------------------------- |
| Operating System | Kali Linux                   |
| Target System    | Ubuntu Linux                 |
| Network Tool     | Wireshark                    |
| Virtualization   | VirtualBox                   |
| Network Type     | Isolated Virtual Lab Network |

## Network Architecture

```text
┌──────────────────┐
│    Kali Linux    │
│  Wireshark Lab   │
│ 192.168.56.105   │
└────────┬─────────┘
         │
         │ Isolated Network
         │
┌────────▼─────────┐
│   Ubuntu Linux   │
│   Target VM      │
│ 192.168.56.104   │
└──────────────────┘
```

## Protocols Analyzed

### IP

Analyzed IPv4 traffic to identify:

* Source IP addresses
* Destination IP addresses
* Protocol information
* Packet length
* Time and packet sequence

### ICMP

Generated ICMP traffic using `ping` and analyzed:

* Echo Request
* Echo Reply
* Source and destination addresses
* ICMP packet details

Example filter:

```text
icmp
```

### DNS

Generated DNS queries and analyzed:

* DNS queries
* DNS responses
* Queried domain names
* Source and destination addresses
* Returned IP addresses

Example filter:

```text
dns
```

Additional filter:

```text
udp.port == 53
```

> Note: DNS traffic may not appear in every capture because systems can use cached results or encrypted DNS. DNS traffic was generated during the lab when necessary.

### TCP

Analyzed TCP communication and examined:

* Source and destination ports
* Sequence numbers
* Acknowledgment numbers
* TCP flags
* Connection establishment

Example filter:

```text
tcp
```

TCP SYN packets:

```text
tcp.flags.syn == 1
```

### HTTP

Analyzed HTTP traffic generated within the isolated lab environment.

Examined:

* HTTP requests
* HTTP responses
* GET requests
* Host information
* Client/server communication

Example filter:

```text
http
```

## Wireshark Display Filters Used

```text
ip
```

```text
icmp
```

```text
dns
```

```text
udp.port == 53
```

```text
tcp
```

```text
tcp.flags.syn == 1
```

```text
http
```

```text
ip.addr == 192.168.56.101
```

```text
ip.addr == 192.168.56.102
```

## TCP Three-Way Handshake

The TCP connection establishment process was analyzed using Wireshark.

```text
Client                         Server

   SYN  ───────────────────────>

        <──────────────── SYN/ACK

   ACK  ───────────────────────>
```

The three packets establish the initial TCP connection between the client and server.

## Packet Analysis Workflow

```text
Generate Network Traffic
          ↓
Start Wireshark Capture
          ↓
Capture Packets
          ↓
Apply Display Filters
          ↓
Identify Protocols
          ↓
Inspect Packet Details
          ↓
Analyze Conversations
          ↓
Follow TCP Streams
          ↓
Document Findings
```

## Evidence

Screenshots and packet-analysis evidence are stored in the `screenshots/` directory.

* `capture-overview.png` — Wireshark packet capture overview
* `ip-analysis.png` — IP traffic analysis
* `dns-analysis.png` — DNS traffic analysis
* `tcp-analysis.png` — TCP traffic analysis
* `http-analysis.png` — HTTP traffic analysis

The packet capture is stored in:

```text
captures/lab-traffic.pcapng
```

## Key Findings

During the lab, network traffic was captured and analyzed at multiple protocol layers.

The analysis demonstrated the ability to:

* Identify communicating hosts
* Determine source and destination addresses
* Filter traffic by protocol
* Analyze DNS queries and responses
* Identify TCP connection establishment
* Examine TCP flags and packet sequences
* Investigate client-server communication
* Use Wireshark to troubleshoot and understand network traffic

## Skills Demonstrated

* Wireshark
* Packet Capture and Analysis
* Network Traffic Analysis
* TCP/IP
* IPv4
* ICMP
* DNS
* TCP
* HTTP
* Network Troubleshooting
* Protocol Analysis
* Wireshark Display Filters
* TCP Stream Analysis
* Technical Documentation

## Security Relevance

Packet analysis is an important skill in cybersecurity and Security Operations Center (SOC) environments.

Wireshark can help security analysts investigate network communications, troubleshoot connectivity issues, identify unusual traffic patterns, and understand how systems communicate across a network.

## Disclaimer

This project was performed in an isolated virtual lab environment using systems controlled for educational purposes.

No unauthorized systems or networks were scanned or analyzed.

## Author

**Cybersecurity / Information Technology Graduate**

Hands-on cybersecurity labs and projects demonstrating practical experience with network security, reconnaissance, packet analysis, and security tools.
