<div align="center">


# Windows Server 2019 Installation and Server Role Configuration in VirtualBox


**Installing and configuring Windows Server 2019 in Oracle VirtualBox, focusing on server role management, static IPv4 configuration, and network administration.**

<p align="center">
  <img src="https://img.shields.io/badge/Project-Windows%20Server-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-v7.2.20-0070C0?style=flat-square&labelColor=000000&logo=virtualbox&logoColor=white" />
  <img src="https://img.shields.io/badge/Windows%20Server-2019-0078D4?style=flat-square&labelColor=000000&logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.3-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-NAT%20Network-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/IPv4-10.0.0.230-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Focus-Server%20Configuration-C00000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Technology-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Platform-GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Practice-Server%20Administration-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Program-IAA-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Mentor-Waqas%20Karim%20(CCIE)-C00000?style=flat-square" />
</p>
</div>

## 🛠️ Windows Server Deployment and Configuration Overview

This project focuses on deploying and configuring **Windows Server 2019** in **Oracle VirtualBox** within a virtualized network environment. The lab covers static IPv4 configuration, server hostname setup, and the implementation of essential Windows Server services, including **Active Directory Domain Services (AD DS), Organizational Units (OUs), Group Policy Objects (GPOs), DHCP, and DNS**.

The project provides hands-on experience in deploying and managing a Windows Server domain environment, creating and managing user accounts, applying security policies, and configuring network services. It aims to develop practical skills in server administration, centralized network management, and domain infrastructure.

## 🎯 Lab Implementation Objectives

The main objectives of this lab are to:

- Install and configure Windows Server 2019 as a virtual machine in VirtualBox.
- Configure the virtual machine's network adapter using a NAT Network.
- Assign a static IPv4 address and configure the server hostname as DC01.
- Establish and test network connectivity from the Windows Server environment.
- Install and configure Active Directory Domain Services (AD DS) using the domain cyberlab.local.
- Create Organizational Units (OUs) and user accounts for Staff, Students, and IT_Admin.
- Configure Group Policy Objects (GPOs) for wireless security, including SSID, WPA3, and 802.1X.
- Install and configure DHCP with scopes for VLAN10 and VLAN20.
- Install and configure DNS with forward and reverse lookup zones.
- Test network communication and verify the configured server services.
- Take a clean virtual machine snapshot for recovery.
- Document the installation, configuration, and testing procedures.
- Develop practical skills in Windows Server administration, domain management, and network infrastructure for future projects.
