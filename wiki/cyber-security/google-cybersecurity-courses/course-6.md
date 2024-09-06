# Course 6: Introduction to Detection and Incident Response

## Module 1: Introduction to Detection and Incident Response

### Incident Response Lifecycle

- What is an incident
- Incident Investigation's 5Ws

### Incident handler's journal

### Incident Response Operations

- CSIRT
  - Roles
    - Analyst
    - Technical Lead/Op(erational)s lead
    - Coordinator
  - Command, Control and Communication
- Security Operation Center
  - relating to blue team
  - Organization
    - Tier 1 Analyst
      - Ticketing system
    - Tier 2 Analyst
    - Tier 3 Lead
    - Manager
- Apache Log4j 2021
- Incident response plan (? differ from lifecycle)
  - Some elements that I don't remember

### Incident Response tools

- Types
  - Detection and management
  - Documentation
  - Investigation
- Documentation
  - Word processors
  - Ticketing system: Jira
- Intrusion Detection System
- Intrusion Prevention System
- Endpoint Detection and response
- SIEM and SOAR Tools
  - SIEM Process: collection and aggregation data -> normalization -> analysis
  - Security Orchestration, Automation and Response: automatically response to an event

## Module 2: Network monitoring and analysis

### Network traffic

- Understanding network traffic flow to detect abnormalities
- Network traffic, network data
- Indicators of compromise
- Data exfiltration

#### Network awareness

- Monitoring your network
  - Flow analysis
    - Using unapproved ports and protocols: command and control
  - Packet payload information
  - Temporal pattern
- Protect Your Network
  - Network Operations Center
  - Tools
    - IDS
    - packet sniffer/network protocol analyzer
#### Data exfiltration attacks

- lateral movement/pivoting

### Capture and view network traffic

#### Network packet

- P-cap
  - Libraries and formats
    - libpcap: linux and macos, tcpdump
    - wincap
    - npcap: Nmap

#### Investigating packet details

- IPv4 and IPv6 format
- Wireshark
  - filtering syntax

### Packet Inspection

#### tcpdump