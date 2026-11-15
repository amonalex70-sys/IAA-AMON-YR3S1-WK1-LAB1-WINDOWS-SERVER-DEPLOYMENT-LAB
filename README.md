<div align="center">

# Windows Server Installation and Server Role Configuration in VirtualBox

**Deploying and configuring Windows Server in Oracle VirtualBox, focusing on server role management, Active Directory, and network administration.**

<p align="center">
  <img src="https://img.shields.io/badge/Project-Windows%20Server-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-v7.2.20-0070C0?style=flat-square&labelColor=000000&logo=virtualbox&logoColor=white" />
  <img src="https://img.shields.io/badge/Windows%20Server-2025-0078D4?style=flat-square&labelColor=000000&logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.3-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-NAT%20Network-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/IPv4-10.0.0.230-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Focus-Server%20Administration-C00000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Technology-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Platform-GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Institution-IAA-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Mentor-Waqas%20Karim%20(CCIE)-C00000?style=flat-square" />
</p>

</div>

## 🛠️ Windows Server Deployment and Configuration Overview

This project involves deploying Windows Server 2025 Standard Evaluation (Desktop Experience) as a virtual machine using Oracle VirtualBox 7.2.20 on a Kali Linux 2026.3 host system.

The deployment establishes a Windows Server environment configured with a NAT Network for virtual network connectivity. The server is assigned a static IPv4 address and configured with the hostname `DC01` before being promoted to a domain controller for the `cyberlab.local` domain.

The configuration covers the installation and management of essential server roles and services, including Active Directory Domain Services (AD DS), DNS, DHCP, and Group Policy. It also includes domain user administration, Organizational Unit (OU) management, wireless security policy configuration, and DHCP scope configuration for VLAN10 and VLAN20.

The overall objective is to build practical experience in Windows Server deployment, domain administration, network services, and enterprise security management within a controlled virtualized environment.

## Lab Implementation Objectives

The main objectives of this lab are to:

- Install and configure Windows Server as a virtual machine using Oracle VirtualBox.
- Configure the virtual network adapter to use a NAT Network.
- Assign a static IPv4 address and configure the server hostname as `DC01`.
- Install and configure Active Directory Domain Services (AD DS) and establish the domain `cyberlab.local`.
- Create Organizational Units (OUs) and user accounts for Staff, Students, and IT_Admin.
- Configure Group Policy Objects (GPOs) to manage wireless network security settings, including SSID, WPA3-Enterprise, and 802.1X.
- Install and configure DHCP scopes for VLAN10 and VLAN20.
- Configure DNS forward and reverse lookup zones.
- Create a clean virtual machine snapshot to support recovery and rollback.
- Document the installation, configuration, and testing procedures.

## 🔐 Lab Purpose and Security Scope

This lab provides a controlled virtual environment for Windows Server administration, network infrastructure management, and cybersecurity practice.

It focuses on deploying and managing essential Windows Server services, including Active Directory Domain Services (AD DS), DNS, DHCP, and Group Policy. The environment also supports practical learning in domain management, user administration, network configuration, and enterprise security policies.

**Security Notice:** This environment is intended strictly for educational purposes, system administration practice, and authorized security testing. All activities must remain within the controlled lab environment or be performed on systems for which explicit permission has been granted. Unauthorized access, modification, or testing of external systems is prohibited.
