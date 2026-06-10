# codealpha_tasks

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

[*] Network Sniffer Initialized... Monitoring live traffic...
[+] Packet Captured: 192.168.1.5 ----> 142.250.190.46 | Protocol: 6 (TCP)
[+] Packet Captured: 192.168.1.1 ----> 192.168.1.5    | Protocol: 17 (UDP)
[+] Packet Captured: 192.168.1.5 ----> 8.8.8.8        | Protocol: 1 (ICMP)

if __name__ == "__main__":
    main()


🎓 TASK 2: Phishing Awareness Training Framework
1. Framework Overview
An educational reference module designed to train corporate employees and individuals to recognize, prevent, and report phishing and social engineering attacks.

2. Key Training Indicators (Red Flags)
Sender Spoofing: Verifying structural mismatches between the email display name and the actual domain syntax in the mail headers.

Psychological Triggers: Identifying manufactured urgency (e.g., "Immediate Account Suspension" or "Unauthorised Transaction Alerts") used to bypass rational judgment.

Technical Validation: Inspecting URLs for typosquatting (e.g., paypa1.com instead of paypal.com) and strictly enforcing HTTPS validation before entering any credentials.

3. Interactive Assessment Design
The training framework includes simulated phishing scenarios and short evaluation quizzes to measure user vulnerability indicators and improve defensive awareness
