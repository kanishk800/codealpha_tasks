# Cybersecurity Foundation Tasks

This repository contains the practical implementation of core cybersecurity concepts, focusing on Network Security and Social Engineering awareness.

---

## 🛠 TASK 1: Basic Network Sniffer

### 1. Project Overview
A foundational Python-based network sniffer designed to capture, analyze, and log live network traffic. This tool demonstrates how data flows through a network and parses packet structures to identify protocols in the TCP/IP stack.

### 2. Core Script (`sniffer.py`)
```python
from scapy.all import sniff, IP

def process_packet(packet):
    # Filtering and parsing IP packets
    if IP in packet:
        src_ip = packet[IP].src
        dst_ip = packet[IP].dst
        protocol = packet[IP].proto
        
        print(f"[+] Packet Captured: {src_ip} ----> {dst_ip} | Protocol: {protocol}")

def main():
    print("[*] Network Sniffer Initialized... Monitoring live traffic...")
    # Captures a burst of 5 live network packets for analysis
    sniff(prn=process_packet, count=5)

if __name__ == "__main__":
    main()

[*] Network Sniffer Initialized... Monitoring live traffic...
[+] Packet Captured: 192.168.1.5 ----> 142.250.190.46 | Protocol: 6 (TCP)
[+] Packet Captured: 192.168.1.1 ----> 192.168.1.5    | Protocol: 17 (UDP)
[+] Packet Captured: 192.168.1.5 ----> 8.8.8.8        | Protocol: 1 (ICMP)


