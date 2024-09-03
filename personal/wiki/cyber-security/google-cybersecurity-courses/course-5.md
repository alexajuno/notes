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
  - 