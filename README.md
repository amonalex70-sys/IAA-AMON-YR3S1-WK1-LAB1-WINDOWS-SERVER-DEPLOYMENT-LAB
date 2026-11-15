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

## ⚙️ Lab infrastructure and system Specifications

| 🧩 Component | ⚙️ Configuration |
|---|---|
| 🖥️ Host OS | Kali Linux 2026.3 |
| 🧠 Host RAM | 8 GB |
| ⚡ Processor | Intel Core i5 |
| 🧰 Virtualization Platform | Oracle VirtualBox 7.2.20 |
| 🪟 Server OS | Windows Server 2025 Standard Evaluation (Desktop Experience) |
| 🧠 Server RAM | 4 GB (4096 MB) |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🖥️ Server Hostname | DC01 |
| 📍 Server IPv4 Address | 10.0.0.230/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 10.0.0.230 |
| 🏢 Domain Name | cyberlab.local |


## ⚙️ Windows Server Setup and Configuration Steps

## Step 1: Add and Install Windows Server 2025 in a Virtual Machine

A virtual machine named `WS2025` was created in Oracle VirtualBox with 4 GB RAM and a NAT Network connection. Windows Server 2025 Standard Evaluation (Desktop Experience) was installed using an ISO image.

**Virtual Machine Specifications**

| Category | Specification |
|---|---|
| VM Name | `WS2025` |
| Guest Operating System | Microsoft Windows Server |
| System Type | Windows Server 2025 (64-bit) |
| Edition | Standard Evaluation (Desktop Experience) |
| Allocated Memory | 4 GB (4096 MB) |
| Network Configuration | NAT Network |

<img width="1356" height="740" alt="Windows Server Virtual Machine" src="https://github.com/user-attachments/assets/3d66150d-ad53-456f-93ad-6c4b77c1ea3a" />

## Step 2: Configure Static IPv4 Address and Server Hostname

A static IPv4 address was assigned to the Windows Server to ensure consistent network identification and communication within the virtual lab. The server hostname was also changed to `DC01` to establish its identity before configuring Active Directory Domain Services (AD DS).

**Network Configuration**

| Category | Specification |
|---|---|
| Hostname | `DC01` |
| IP Address | `10.0.0.230` |
| Subnet Mask | `255.255.255.0` |
| Default Gateway | `10.0.0.1` |
| Preferred DNS Server | `10.0.0.230` |
| Alternate DNS Server | `8.8.8.8` |
| Network Address | `10.0.0.0/24` |

<img width="690" height="614" alt="WS-Static IPv4 Configuration" src="https://github.com/user-attachments/assets/703d19db-99f9-4468-84c8-982375943265" />

## Step 3: Install and Configure Active Directory Domain Services (AD DS)

The Active Directory Domain Services (AD DS) role was installed on `DC01`, and the server was promoted to a domain controller by creating a new forest named `cyberlab.local` for centralized domain authentication and administration.

<img width="1088" height="791" alt="WS-AD DS complete" src="https://github.com/user-attachments/assets/103df75d-3f86-4f51-8674-44ed0d843c27" />

## Step 4: Create Organizational Units (OUs) and Domain User Accounts

Organizational Units (OUs) were created in Active Directory to organize Staff, Students, and IT_Admin accounts. Domain user accounts were then created and assigned to their respective OUs for centralized user management and administration.

<img width="1088" height="791" alt="WS-OU   USERs" src="https://github.com/user-attachments/assets/c523c65a-d6e3-42e1-8afa-1d5662651312" />

## Step 5: Configure Group Policy Objects (GPOs)

Group Policy Objects (GPOs) were created and configured to manage wireless network security settings, including SSID, WPA3-Enterprise, and 802.1X authentication.

## Step 6: Install and Configure DHCP Server

The DHCP Server role was installed and configured on `DC01`, with DHCP scopes for VLAN10 and VLAN20 to manage IP address allocation and network configuration for client devices.

## Step 7: Install and Configure DNS Server

The DNS Server role was installed and configured to provide name resolution within the `cyberlab.local` domain, allowing domain-joined computers to locate the domain controller and communicate using hostnames.

