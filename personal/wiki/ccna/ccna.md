# CCNA 200-301 

## Introduction

- Network: resources sharing telecommunicatively
  - nodes
    - end points/hosts: server, clients
      - client: access services of servers
      - server: send services to clients
    - switches
      - devices -> switch: LAN
    - routers
    - firewalls
      - can be place inside or outside router
      - there are configured rules in firewalls
      - NGFW
      - host-based firewalls (software) and network firewalls (hardware)

## Interfaces and Cables

- Switches
  - Register Jack - 45
- Ethernet
  - Network protocols/standards
- Speed is measured by bits per second
- Ethernet standards: IEEE 802.3
  - Types of LAN Technology
- UTP Cables 
  - Unshielded: against electrical interference
  - Twisted: against electromagnetic interference
  - Pair
  - 10base-t and 100base-t: 2 pairs: 1-2 and 3-6 form full-duplex
    - Something related to NIC here
    - straight-through cables: 
    - cross-over cables: for same types of devices
      - I haven't understand these types of cables yet. Is this related to physic cables or protocols?
    - Auto MDI-X
  - 1000base-t and 10gbase-t: 4 pairs, bidirectional
  - Can leak signals
- Fiber-optic connections
  - Small Form-factor Pluggable Transceiver
  - Structure: fiberglass core, cladding, protect
  - Multimode fiber
  - Single-mode fiber
    - I haven't understood the mechanics of this one, that leads to differences with multimode
  - Standards

## OSI Model and TCP/IP Suite

- What is a networking model
- Open Systems Interconnection  
  - Created by ISO
  - 7 layers
    - Application
    - Presentation: encryption and format translation between application and network
    - Session: manage connection between application
    - Transport: segments and reassembles
    - Network: connection between networks using IP addresses including logical addressing, path selection 
    - Data Link: node to node connectivity
  - Protocol Data Units: segment, packet, frame, bit
- TCP/IP Suite

## Intro to the CLI

- What is a CLI?
- interface used for Cisco devices configuration
- How to connect to a Cisco device?
  - Bring your laptop to the device and use console ports to connect
  - Rollover cable (rj45 -> db8) + adapter (db8 -> usb)
  - Terminal emulator
    - user exec mode
    - privileged mode: enable command
    - global configuration
    - enable password
    - running config / start-up config
    - Summary: some modes, you can add password to privilege mode, manage configuration

## Ethernet LAN Switching

- What is a LAN
- Ethernet frame
  - Header
    - Preamble: 7 bytes
    - Start Frame Delimiter: 1 byte
    - Destination, Source: 6 bytes (MAC address)
    - Type/Length: 2 byte
  - Trailer: Frame Check Sequence: 4 bytes
    - Algorithms
  - Minimum size: 64 bytes
    - Padding bytes
- MAC address: 6 bytes
  - first 3 bytes are the Organizational Unique Identifier
  - last 3 bytes are unique to the device
- Address Resolution Protocol
  - Request and reply message
- MAC address table: arp -a 
  - clear mac address-table dynamic interface &lt;address-id&gt;
  - show mac address-table
- Ping: use to test reachability
  - ping [ address ] size [ number ]
  - ICMP Echo request/reply

## IPv4 Addressing

- IPv4 Header
- Network and host portion in an ip address
- IPv4 address classes
  - class D: multicast
  - class E: reserved (exprimental)
  - loopback addresses: 127.*.*.*
  - netmask
  - Network address
  - Broadcast address
- ip config
  - interface g0/0
    - ip address &lt;address&gt; &lt;subnet mask&gt;
  - show ip interface brief
    - interface/ip-address/ok?/method/status/protocol
  - show interface g0/0
  - show interface description

