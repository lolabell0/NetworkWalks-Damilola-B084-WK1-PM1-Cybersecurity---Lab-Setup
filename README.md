<div align="center">

# Virtual Cybersecurity Lab & Penetration Testing Environment
**A comprehensive guide to deploying a secure, isolated environment for ethical hacking practice and vulnerability assessment.**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.3-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-B084-404040?style=flat-square&labelColor=C00000" />
 

---

## Project Overview

This project outlines the configuration of a **virtual cybersecurity and penetration-testing laboratory** using Oracle VM VirtualBox and Kali Linux. The goal of this environment is to provide a fully controlled, sandboxed workspace where security tooling, reconnaissance, port scanning, and vulnerability assessments can be executed securely. 

The lab is isolated on a dedicated virtual network, permitting future expansion by introducing vulnerable target machines for authorized security experimentation.

---

## Objectives

The primary objectives of this project include:
- Installing and configuring Oracle VM VirtualBox.
- Deploying and importing Kali Linux as a guest virtual machine.
- Establishing an isolated **NAT Network** specifically for lab operations.
- Configuring robust networking and static IP routing inside Kali Linux.
- Validating end-to-end network reachability and external name resolution.
- Capturing a clean operational baseline via VM snapshots.
- Documenting the deployment procedures for reproducibility.

---

## Purpose of the Lab

This environment is built to offer a secure space for practical cybersecurity learning and authorized assessments.
## Lab Configuration

|  Component         | Configuration      |
| ------------------ | ------------------ |
|  Host OS           | Windows 10         |
| Host RAM           | 8 GB               |
|  Hypervisor        | VirtualBox         |
| Security OS        | Kali Linux 2026.3  |
| Kali RAM           | 2048 MB            |
| Virtual Network    | NAT Network        |
| Network Address    | 10.0.0.0/24        |
|  Kali IP Address    | 10.0.0.2/24       |

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux VM
**Tool:** 7-Zip

---

## Step 2. Install VirtualBox

VirtualBox was installed as the hypervisor.

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox using IPv4 Prefix:  10.0.0.0/24

!C:\UScreenshots

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


---

## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:

```text
RAM: 2048 MB
```
![](3-screenshot-kali-linux.png)
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

## Step 5: Configuration of the Kali linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address- 10.0.0.3


![](4-screenshot-kali-network-settings.png)

---

## Step 6: VM Snapshot

# Problems Encountered & Solutions


## Problem 1: Extracting the kali zip file and importing to virtual box
After donloading m
---

## Problem 2: VirtualBox VT-x / Virtualization Error

The VM initially failed to start because hardware virtualization was disabled in the system firmware/BIOS.

The issue was resolved by:

1. Restarting the computer.
2. Entering BIOS/UEFI settings.
3. Enabling Intel VT-x / hardware virtualization.
4. Saving the configuration.
5. Restarting the computer.
6. Starting the Kali VM again.

After enabling virtualization, the VM started successfully.


---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---


# Author

Damilola Bello 
Cybersecurity Professional B082

LinkedIn: [https://www.linkedin.com/in/waqaskarim/](https://www.linkedin.com/in/waqaskarim/)

---

## 📌 Project Information

**Program Name:** Cybersecurity at N
