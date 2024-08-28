# Course 4: Tools of the Trade: Linux and SQL

## Module 1: Introduction to OS

### Getting started

### Introduction to OS

- Operating System
- Compare OSs
  - Common OSs
    - ChromeOS and Chromium OS
  - OS and vulnerabilities
    - Legacy OS
    - Other vulnerabilites: There are websites of OS providers that inform about present vulnerabilities

### How OSs Work

- Pressing power button -> BIOS/UEFI starts -> bootloader runs OS
  - BIOS ain't scanned by antivirus programs
- Resource allocation by OS
- Virtualization Technology
  - What is a VM
  - Benefits
    - Security: providing a sandbox to play around. But there are chances that malware can escape virtualization and attack the host
    - Efficiency: Multiple VM on a single physical hardware
    - Managing VMs: hypervisor. You will want to be familiar with Kernel-based VM
  - Other forms of virtualization: many more but they don't tell the detail

### The User Interface

#### GUI vs CLI

- Advantages of CLI in Cybersecurity
  - Efficiency
  - History file

## Module 2: The Linux OS

### All about Linux

- Introduction
  - History of Linux
  - Linux is FOSS
  - Some example of Linux usage
  - Each distribution has its advantages in cybersecurity
- Linux architecture
  - User
  - Application
    - Package manager
  - Shell
  - Filesystem hierarchy standard
  - Kernel
  - Hardware
    - Peripheral
    - Internal

### Linux distributions

#### KALI LINUX

- Should be used on VMs
- Pen testing tools
  - Metasploit
  - Burp Suite
  - John the Ripper
- Digital forensic works
  - tcpdump
  - Wireshark
  - Autopsy

#### More distros

- Ubuntu
  - Relating to cloud computing
- Parrot
  - Like KALI LINUX but more user-friendly
- Red Hat Enterprise Linux
  - for enterprises
- CentOS

#### Package Managers

- Introduction
  - Package
- Types of package managers
- package management tools
  - pmt allow users perform basic tasks easier
  - Advanced Package Tool (APT): Debian distros
  - Yellowdog Updater Modified: RedHat distros

### The Shell

- Shell, command
- Types of shells
- Input and output
  - echo
  - expr
  - clear

## Module 3: Linux commands in the Bash shell

### File navigation

- Filesystem Hierarchy Standard
  - /: root
  - Standard directories: using `man hier`
- Navigating filesystem: pwd, ls, cd
- Reading file content: cat, head, less, tail

### Manage file content

- Basic filtering
  - grep
  - piping
  - find
- Create and modify dirs and files
  - mkdir
  - rmdir
  - touch
  - rm
  - mv
  - cp
  - nano
  - output redirection with > and >>

### Authenticate and authorize users

- Permission and authorization
  - Types of permissions
    - Read
    - Write
    - Execute
  - Owners
    - User
    - Group
    - Other
    - 10 chars permissions
  - ls [ -l ] [ -a ]
- Changing permissions
  - chmod g+w,o-r access.txt
- Add and delete users
  - root user/superuser
    - security risks
    - irreversible mistakes
    - accountability
  - sudo: superuser-do
    - grant access via a sudoers file
    - useradd
      - -g, -G
    - userdel
    - usermod
    - chown
  - ? I haven't understood about users in a Linux system

### Get Help in Linux

- Linux community
- man, whatis, apropos
  
