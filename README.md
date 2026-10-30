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

---

## Step 2. Install VirtualBox

VirtualBox was installed as the hypervisor.

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox using IPv4 Prefix:  10.0.0.0/24

<img width="1920" height="1080" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/1c9ea4ee-42ee-4979-a9c6-791dd072312a" />

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


---

## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:


<img width="1920" height="936" alt="VirtualBox_kali-linux-2026 3-virtualbox-amd64_30_10_2026_18_05_32" src="https://github.com/user-attachments/assets/43c1c593-41c2-4940-8d2a-e5ea554f65bc" />

A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

## Step 5: Configuration of the Kali linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address- 10.0.0.3


<img width="1920" height="936" alt="VirtualBox_kali-linux-2026 3-virtualbox-amd64_30_10_2026_13_10_47" src="https://github.com/user-attachments/assets/f7d09ead-2a21-4a88-b4eb-09646ad7a720" />


---

## Step 6: VM Snapshot
<img width="960" height="595" alt="Kali snapshot" src="https://github.com/user-attachments/assets/c2d57b4e-5109-43b7-a99c-71394454d677" />


# Problems Encountered & Solutions


## Problem 1: Extracting the kali zip file and importing to virtual box

After downloading kali linux from the recommended site, i had a challenge imporing it into virtualbox. I solved this challenge by first extracting kali linux using 7zip and then importing the virtualbox machine definition into the virtual box.
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

# What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice. I also learned to extrct files using 7zip and enable virtualization.


# Author

Damilola Bello 
Cybersecurity Professional B084

LinkedIn: [https://www.linkedin.com/in/damilolabelloo/](https://www.linkedin.com/in/damilolabelloo/)

---

