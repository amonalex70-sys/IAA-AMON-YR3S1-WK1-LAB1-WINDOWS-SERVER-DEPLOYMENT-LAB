<div align="center">

# Windows server installation and server role configuration in VirtualBox

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

## 🛠️ Windows server deployment and configuration overview

This project involves deploying Windows Server 2025 Standard Evaluation (Desktop Experience) as a virtual machine using Oracle VirtualBox 7.2.20 on a Kali Linux 2026.3 host system.

The deployment establishes a Windows Server environment configured with a NAT Network for virtual network connectivity. The server is assigned a static IPv4 address and configured with the hostname `DC01` before being promoted to a domain controller for the `cyberlab.local` domain.

The configuration covers the installation and management of essential server roles and services, including Active Directory Domain Services (AD DS), DNS, DHCP, and Group Policy. It also includes domain user administration, Organizational Unit (OU) management, wireless security policy configuration, and DHCP scope configuration for VLAN10 and VLAN20.

The overall objective is to build practical experience in Windows Server deployment, domain administration, network services, and enterprise security management within a controlled virtualized environment.

## Lab implementation objectives

The main objectives of this lab are to:

- Install and configure Windows Server as a virtual machine using Oracle VirtualBox.
- Configure the virtual network adapter to use a NAT Network.
- Assign a static IPv4 address and configure the server hostname as `DC01`.
- Install and configure Active Directory Domain Services (AD DS) and establish the domain `cyberlab.local`.
- Create and manage Organizational Units (OUs) and user accounts in Active Directory according to the lab's organizational structure.
- Configure Group Policy Objects (GPOs) to manage wireless network security settings, including SSID, WPA3-Enterprise, and 802.1X.
- Install and configure DHCP scopes for VLAN10 and VLAN20.
- Configure DNS forward and reverse lookup zones.
- Create a clean virtual machine snapshot to support recovery and rollback.
- Document the installation, configuration, and testing procedures.

## 🔐 Lab purpose and security scope

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


## ⚙️ Windows server setup and configuration steps

## Step 1: Add and install windows server 2025 in a Virtual Machine

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

<img width="805" height="700" alt="WS-Static IPv4 Configuration" src="https://github.com/user-attachments/assets/3b8cfa1b-d81f-4c6e-9336-d46a28d16f32" />

## Step 3: Install and Configure Active Directory Domain Services (AD DS)

The Active Directory Domain Services (AD DS) role was installed on `DC01`, and the server was promoted to a domain controller by creating a new forest named `cyberlab.local` for centralized domain authentication and administration.

<img width="1088" height="791" alt="WS-AD DS complete" src="https://github.com/user-attachments/assets/103df75d-3f86-4f51-8674-44ed0d843c27" />

## Step 4: Create Organizational Units (OUs) and Domain User Accounts

Organizational Units (OUs) were created in Active Directory to organize domain users according to the lab's structure. User accounts were then created and assigned to their respective OUs to support centralized user management and administration.

<img width="1088" height="791" alt="WS-OU   USERs" src="https://github.com/user-attachments/assets/c523c65a-d6e3-42e1-8afa-1d5662651312" />

## Step 5: Configure Group Policy Objects (GPOs)

Group Policy Objects (GPOs) were created and configured to manage wireless network security settings, including SSID, WPA3-Enterprise, and 802.1X authentication.

<img width="850" height="734" alt="Creating GPO Link " src="https://github.com/user-attachments/assets/7296b13f-eddc-433a-9e9f-59e9a9c6fa3a" />


## Step 6: Install and Configure DHCP Server

The DHCP Server role was installed and configured on `DC01`, with DHCP scopes for VLAN10 and VLAN20 to manage IP address allocation and network configuration for client devices.

<img width="805" height="700" alt="DHCP Scope" src="https://github.com/user-attachments/assets/67edc35f-5e4a-484f-a43f-1dd779315626" />


## Step 7: Install and Configure DNS Server

The DNS Server role was installed and configured to provide name resolution within the `cyberlab.local` domain, allowing domain-joined computers to locate the domain controller and communicate using hostnames.

<img width="805" height="700" alt="DNS" src="https://github.com/user-attachments/assets/50469013-1a45-421c-864e-ea96413308c0" />


# 🐞 Problems Encountered & Solutions

Documenting troubleshooting procedures helps identify configuration issues, improve system reliability, and provide useful references for future lab activities.

## Problem 1: DHCP Server Configuration Error (Error 20070)

During DHCP Server configuration, I encountered **Error 20070** when attempting to configure and authorize the DHCP Server while logged in with a standard user account. The configuration could not be completed because the account did not have the required administrative privileges.

**Solution:** I switched from the standard user account to an account with the appropriate administrative privileges and repeated the DHCP Server configuration. The configuration and authorization process completed successfully.

> **Note:** DHCP Server configuration and authorization require appropriate administrative permissions, particularly membership in the relevant domain administrative groups.

---

# 💡 What I Learned

Through this project, I gained practical experience installing, configuring, and administering a Windows Server 2025 environment using Oracle VirtualBox.

The most important concepts I learned include:

### 1. Virtualization and Server Installation

I learned how to create and configure a virtual machine in Oracle VirtualBox and install Windows Server 2025 Standard Evaluation (Desktop Experience). I also gained experience allocating system resources and configuring virtual hardware.

### 2. Initial Server Configuration

I learned how to configure essential server settings, including the computer name, hostname, network adapter, and system administration settings required to prepare a server for deployment.

### 3. Network Configuration

I learned how to configure a static IPv4 address, subnet mask, default gateway, and DNS settings. I also gained experience testing network connectivity between virtual machines.

### 4. Active Directory Domain Services (AD DS)

I learned how to install and configure Active Directory Domain Services and promote a Windows Server machine to a domain controller. This introduced me to centralized authentication, directory services, and domain-based network administration.

### 5. Organizational Units and User Account Management

I learned how to create Organizational Units (OUs) and domain user accounts in Active Directory. I also gained an understanding of how directory objects can be organized to support centralized user and administrative management.

### 6. DHCP Server Installation and Configuration

I learned how to install and configure the DHCP Server role, authorize the DHCP server in Active Directory, and understand how DHCP automatically assigns IP addresses and other network configuration parameters to client machines.

### 7. DNS Server Installation and Configuration

I learned how to install and configure the DNS Server role and understand its importance in domain environments. DNS enables domain name resolution and supports communication between domain-joined computers and the domain controller.

### 8. Troubleshooting and Documentation

I developed practical troubleshooting skills by investigating DHCP configuration and authorization errors, identifying account permission requirements, switching to an appropriately privileged account, and successfully completing the configuration.

### 9. Windows Server Administration

I established a foundation in Windows Server administration, including server deployment, domain controller management, centralized user administration, and network service configuration.

---

# 🔐 Security & Ethical Use

This laboratory environment is designed strictly for educational purposes, practical Windows Server administration, and authorized cybersecurity training.

All configuration, testing, and security assessments must be conducted within the controlled laboratory environment or on systems for which explicit authorization has been granted.

---

# 🔗 Tools & Resources

- **Oracle VirtualBox:** [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
- **Windows Server:** [https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025)
- **Microsoft Learn:** [https://learn.microsoft.com/en-us/windows-server/](https://learn.microsoft.com/en-us/windows-server/)

---

# 👤 Author

**Amon Alex**
Cybersecurity Student | Electronics, Telecommunications & Cybersecurity

**LinkedIn:** [Amon Alex](https://www.linkedin.com/in/amon-lowasa-60877a42a/)

---

# 📌 Project Information

**Program Name:** Cybersecurity at IAA
**Project:** Windows Server 2025 Installation and Configuration
**Virtualization Platform:** Oracle VirtualBox 7.2.20
**Server Edition:** Windows Server 2025 Standard Evaluation (Desktop Experience)

**Repository:** GitHub



