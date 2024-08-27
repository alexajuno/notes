# Course 3: Connect and Protect: Networks and Network Security

## Module 1: Networks

### Introduction

- What are networks?
- Network tools?
- Cloud computing
- Cloud network
- About cloud services. I mean we still need network tools to link computers within an org, so when refering to hybrid cloud env, I think the only thing that differ is storage. Is it true?
- Software-defined networks

### Network communication

- Packet
  - Header (ip/mac/protocol number?)
- Bandwith
- Packet sniffing
- TCP/IP
  - TCP?
  - IP?
  - Port
  - TCP/IP model
- OSI model

### Local and wide network communication

- IP address
  - IPv4
  - IPv6
- MAC address

## Module 2: Network operations

### Protocols

- What are network protocols?
- TCP
- Address Resolution Protocol: Mapping IP to MAC within the same network
- HTTPS
- DNS
- Secure Socket layer
- Network Address Translation: private IP -> public IP
- Dynamic Host Configuration Protocol: assigns dynamic IP address for each device
  - DNS Server?
  - Default gateway?
- Telnet
- Secure shell
- Post office protocol

#### Wireless Secure Protocols

- IEEE 802.11: Wi-fi
- Wireless Application Protocol

### System Identification

#### Firewall

- What is a firewall?
- Cloud-based firewall
- Stateful and stateless firewall
- NGFW

#### Subnetting and CIDR

- Security zone
  - Uncontrolled
  - Controlled zone
    - Demilitarized zone
    - Internal zone
    - Restricted zone
- network segmentation
- Subnet
- Classless Inter-Domain Routing notation for subnetting

#### Proxy Servers

- What is it?
- Types
  - Forward proxy server
  - Reverse proxy server
- Virtual networks and privacy

## Module 3: Secure against network intrusion

### Intrusions

- Network interception attacks
  - Packet sniffing
- Backdoor attack
  - DoS attack
- Possible impacts

### Denial of Service

- Flood network server with traffic
- DDoS
- SYN flood attack
- ICMP flood attack
- Ping of death
- Network protocol analyzers
  - tcpdump
- Real life DDoS attack

### Network attack tactics and defense

- Packet and packet sniffing
- Passive and active packet sniffing
- How to defense
  - SSL/TLS
  - VPNs

#### IP Spoofing

- On-path attack
- Replay attack
- Smurf attack
- How to defense

## Module 4: Security Hardening

### Intro

- What is security hardening, attack surface, pen test?

### OS hardening

- What is an OS?
- Why insecure OS can lead to the whole network being compromised?
- Regular and once-time tasks

  - Patch updates
  - Baseline configuration/image
  - Hardware and software disposal
  - Strong password policy
  - MFA

- Brute-force attack
  - Simple bf
  - Dictionary attack
- Assessing vulnerabilities
  - Virtual Machines
  - Sandbox env
- Preventing measures
    - Salting and hashing
    - MFA and 2FA
    - CAPTCHA and reCAPTCHA
    - Password policies
