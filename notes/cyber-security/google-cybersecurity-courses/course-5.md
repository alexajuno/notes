# Course 5: Assets, Threats and Vulnerabilities

## Module 1: Introduction to asset security

### Introduction to assets

#### Asset security

- What is risk
- Security risk planning
  - Three elements: assets, vulnerabilities, threats
- Threat: intentionally and unintentionally
- Vulnerability: technical and human

#### Asset classification

- Classical classification: public, internal-only, confidential, restricted

### Digital and physical assets

- Information and data, what are the differences?
- States of data: in use, in transit, at rest
- InfoSec

#### The emergence of cloud security

- Cloud is developing fast
- Cloud-based services
  - SaaS
  - PaaS
  - IaaS
  - I haven't understood what the differences are
- Cloud security
  - Challenges
    - Misconfiguration
    - Cloud-native breaches
    - Access monitoring difficulties
    - Meeting regulatory standards

### Risk and asset security

- Elements of a security plan: policies, standards, procedures
  - It seems that policies -> standards -> procedures
- NIST Cybersecurity Framework
  - Compliance
  - Regulations
  - Components
    - Core
      - Five functions: Identify, Protect, Detect, Response, Recover
    - Tiers: level 1 -> 4, how sophisticated a security system is
    - Profiles: I haven't fully understood this yet
  - Implementations

## Module 2: Proect organizational assets

### Safeguard information

#### Security Controls

- Types: technical, operational, managerial
- Information privacy
- Principle of least privilege
  - Determine access and authorization
    - common types of accounts: guess, user, service, privileged
  - Auditing privileges
    - Common approaches
      - usage
      - privilege
        - privilege creep
      - account change: authenticate changes should be made by authored users

#### Data Lifecycle

- The data lifecycle: collect, use, store, archive, destroy
- Data governance
  - Policies
  - Individual categorization: owner, custodian, steward
- Protecting data at each stage
- Legally protected information
  - Types of information must be protect by default
    - Personal Identifiable Information: can be use to locate or contact someone
    - Protected Health Information:
    - Sensitive PII

#### Information Privacy: Regulations and Compliance

- info security and privacy
- why privacy matter in security
  - the more data, the more vulnerable it is to breaches and threats
- notable privacy regulations
  - General Data Protection Regulation
    - by EU
  - Payment Card Industry Data Security Standard
    - financial industry
  - Health Insurance Portability and Accountability Act
    - About health
- Security Assessments and audits

### Encryption methods

#### Public key infrastructure

- Process
  - Exchange of encrypted information
    - Asynmetric encryption: the use of public and private key pair
    - Synmetric encryption: faster, but more vulnerable using a single secret key
  - Establish trust using a system of digital certificates
    - Digital certificate: verifies the identity of public key holder
      - I haven't understood the detail

#### Encryption

- Key length
- Approved algorithms
  - synmetric
    - 3DES
    - AES
  - asyn
    - RSA
    - DSA
  - Generating keys
    - OpenSSL
- Obscurity isn't security: Kerckhoffs's principle
  - Encryption is everywherekkkk

#### Non-repudiation and hashing

- hash function
- non-repudiation

#### The evolution of hash function

- Origins of hashing
  - Message Digest 5
  - hash collision
- Next-generation hashing
  - Secure Hashing Algorithms
- Secure password storage: instead of storing passwords themselves, we store their hash values
  - Rainbow table
- Adding some salt

### Authentication, Authorization and accounting

- Access controls
- AAA framework
  - Authentication: who are you?
    - Factors: knowledge, ownership, characteristic
    - Single Sign-On + MFA

#### SSO and MFA

- SSO
  - benefits: improves ux, lower costs, improve overall security
  - password fatigue
  - how it works
    - uses third-party services to prove user to be
    - protocols: LDAP, SAML
  - limitations: all eggs in a singel basket
- MFA

#### Authorization mechanisms

- two principles
  - separation of duties
  - principles of least privilege
- HTTP basic auth and OAuth
- API Token

#### Audit

- access log
- session
  - session cookies
  - sessionID
  - session hijackingo

#### Identity and Access Management

- user provision/deprovision
- granting authorization
  - Mandatory Access Control
  - Discretionary Access Control
  - Role-based Access Control
- Access Control Technologies
  - Security is more about combining a bunch of tools. It's important to configure them to provide a secure env

## Module 3: Vulnerabilites in system

### Flaws in a system

#### Vulnerabilities

- Vulnerability management: identify, consider potential exploits, prepare defenses, evaluate them
- zero-day exploit

#### Defense in-depth strategy

- Five layers
  - Perimeter
  - Network
  - End point
  - Application
  - Data

#### Common vulnerabilites and exposures

- CVE list
  - criteria: independent of other issues, recognized as a potential risk, submitted with supporting evidence, only affect one codebase
- CVE Numbering Authority
- NIST National Vulnerabilities Database
  - CVSS Score
- The OWASP Top 10
  - Common vulnerabilites
    - Broken access control
    - Cryptographic failures
    - Injection

#### Open Source Intelligence

- OSINT
- Information vs intelligence
- Intelligence improve decision-making
- Tools
  - VirusTotal
  - MITRE ATT&CK
  - OSINT Framework
  - Have I been pwned

### Identify system vulnerabilities

#### Vulnerabilities Assessment

- steps: identification, analysis, risk assessment, remediation

#### Approaches to vulnerability scanning

- Vulnerability scanner
  - scanning can cause issues even it meant to be non-intrusive
- Performing scans
  - External and internal scans: simulate attacks
  - Authenticated vs non
  - Limited vs comprehensive

#### The Importance of updates

- Patching gaps in security
- Common update strategies: auto and manual
- End-of-life software
- patches vs updates vs upgrades

#### Penetration testing

- Learning from varied perspectives
- Pen test strategies
  - Open-box testing
  - Closed-box testing
  - Partial knowledge testing/gray-box testing
- Become a pen tester

### Cyberattackers mindset

#### Protect all entry points

- Analyze attack surface: both physical and digital
- Security hardening

#### Attacker mindset

- Being prepared for everything
- Simulating threats
  - blue and red teams exercises
- Scanning for trouble

#### Types of threat actors

- Threat actors
  - categories: competitors, state actors, criminal syndicates, insider threats, shadow IT
  - types of hackers: 
- Advanced persistent threats
- Access points
- Capture the Flags (CTF)

#### Pathway through defenses

- Attack vectors
- practicing attacker mindset
  - identify a target
  - determine how the target can be accessed
  - evaluate attack vectors that can be exploit
  - find the tools and methods
  - note: step 2 to 4 kinda similar I would say
- Defending
  - Educating users
  - Principles of least privilege
  - security controls and tools
  - building a diverse security team

#### Fortify against brute force attacks

- reverse brute-force attack
- credential stuffing
- Tools
  - Aircrack-ng
  - Hashcat
  - John the ripper
  - Ophcrack
  - THC Hydra
- Prevention measures
  - hashing and salting
  - MFA
  - CAPTCHA
  - Password policies

- USB Baiting

- Note: I haven't fully understood the 5 layers of defense in depth

## Module 4: Threats to Assets Security

### Social Engineering

- Exploits human errors
- Steps: Prepare(? isn't anything has to be prepared), Establish trust, persuasion tactics (? isn't this the same as the above step), disconnect
- Defenses
  - Implement managerial controls
  - Stay informed of trends
  - Sharing your knowledge
- Signs
  - Baiting
  - Phising
  - Quid pro quo
  - Tailgating/piggybacking
  - Watering hole
- Encouraging caution
  - Stay alert
  - Be cautious
  - Control curiosity

#### Phising

- Phishing kit
  - Mallicious attachment
  - Fake data-collection forms
  - Fradulent web links
  - Smishing
  - Vishing

### Malware

- Types
  - Virus: causes damage
  - Worm: duplicate and spread
  - Trojan horse: appears as legitimate software
  - Ransomware
  - Spyware: steal info
  - Fileless
  - Scareware
  - Rootkits: dropper + loader
  - Botnet
- Cryptojacking

### Web based exploits

- Cross-site scripting
  - Types
    - Reflected XSS
    - Stored XSS
- Databases 
  - SQL Injection
    - Types
      - In-band: most common, using the same communication channel
      - out-of-band: very uncommon
      - Inferential
    - Prevention
      - Prepared statement 
      - Input sanitization
      - Input validation

### Threat Modeling

- Usually performed by professionals
- Steps: I don't bother to remember lol
- PASTA
  - Define the scope
    - business and security objectives
    - technical scope
- and various frameworks