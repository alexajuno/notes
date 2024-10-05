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

## Module 3: Incident Investigation and Response

### Incident detection and verification

#### Detection and Analysis phase

- detection by tools
- analysis include investigate and validate alerts
- challenges
  - impossible to detect everything
  - high volumes of alerts

- incident detection methods
  - Threat hunting
  - Threat intelligence: information gathered from resources like
    - industry reports
    - government advisories
    - Threat data feeds
    - Threat intelligence platform to centralize large amount of data from intelligence
  - Cyber deception
    - Honeypots

#### Indicators of compromise

- Indicators of attack
- Pyramid of pain

#### Analyze IoC

- Adding context by using threat intelligence can help with IoC
- The power of Croudsourcing
  - Information Sharing and Analysis Centers
  - Open-source Intelligence
  - VirusTotal: data you submitted will be public  
- Other tools
  - MalwareBazaar: malware samples
  - Some free web-based files and sites scanners

### Create and use documentation

- Benefits: transparent, standardized, clear
- Chain of custody: documeting incidents - transparency
- Playbook: automatical level

### Response and Recovery

- Triage: manage resources
  - Process: receive and assess, assign priority, collect and analyze
- Containment, eradication and recovery
- Business continuity plan
  - differs from disaster recovery plan
  - site resilience

### Post-incident activities

- Final report: I'll reference to the format later

## Module 4: Network traffic and logs using IDS and SIEM tools

### Log Overview

- log, log analysis, log types: system, network, app, etc.
- Log management: what to log, overlogging, log retention, log protection
- variations
  - syslog
  - json
  - xml
  - csv
  - cef (common event format)

### IDS Overview

- Telemetry
- Signature/Abnomaly analysis
- Detection Signature
  - action to take
  - header: like packet's header
- Suricata
  - signature/rule config
  - eve json

### SIEM Tools Overview

- 