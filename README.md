# Building_MY-HOME-LAB
This project is a personal home lab setup using VirtualBox for virtualization. It includes multiple virtual machines for exploring cybersecurity, networking, and system administration in a safe, isolated environment.
# 🖥️ Virtualization Machines and Hypervisors

In this module, we have learned about:

1. How virtualization works  
2. What a hypervisor is  
3. Some of the core benefits of virtualization  
4. Different brands & software commonly available in the market used for virtualization  
5. What a container is & how it differentiates from a virtual machine  

---

> **Virtualization is a process of creating a software-based version of something that would typically require its own hardware.**

We can virtualize many things such as:  
- Network Equipment  
- Storage Mediums  

But in this lesson, we have focused on **virtualizing an entire computer**, which is often referred to as a **Virtual Machine**.

---

### 💻 What is a Virtual Machine?

**A Virtual Machine, commonly referred to as a VM, is a software-based virtualization of an entire computer, including its operating system and any application we would like to install on it.**     

> If I want to, I can even run multiple virtual machines from my computer so long as I have the resources to handle it.

---

### 🧩 What is a Hypervisor?

In order for virtualization to take place, we need a piece of software on the host computer that's able to split and allocate those hardware resources to the virtual machine — and that piece of software is referred to as a **hypervisor**.

> **Hypervisor is responsible to actually then partition up and allocate out the resources of the host OS to the virtual machines.**

---

### 🔸 Types of Hypervisors

There are two types of Hypervisors:

1. **Type 1**  
2. **Type 2**

We will be using a **Type 2 hypervisor**.  
> One of the downsides of Type 2 hypervisors is that they are less efficient because we have got this Base OS that we still have to install on the system.

For example:  
If we just wanted to be hosting virtual machines and that’s all it's going to be used for, we don't want to be wasting resources running a Base OS — because it can be quite resource hungry and take up some of that underlying hardware that we have.

Key hardware impacted:
- CPU
- RAM

---

### 🛠️ Two Most Common Type-2 Hypervisors:
1. VMware Workstation (Type-2)  
2. VirtualBox - Oracle  

[Virtualization Explained](![Screenshot 2025-06-03 121810](https://github.com/user-attachments/assets/5eae74d5-7dca-4c2f-b8f1-54f27af93c48)

**Virtualization Explained by Andrew Bellini**

---

### 🔍 Difference Between Type 1 and Type 2 Hypervisors

#### 🧱 Type-1 Hypervisor
- Installed directly on the **bare metal**, so there is no underlying operating system that the hypervisor is installed on.
- It’s actually installed almost like its own operating system directly onto the host computer.

Common names for Type-1 hypervisors:
- Bare Metal  
- More Efficient  
- More commonly used inside of an **enterprise**, **business**, or **commercial** environment

> The reason for this is that they would like to be able to stand up multiple or a cluster of virtual machines on a server — and that server’s dedicated purpose is just to host those virtual machines that multiple people can interact with and can be spun up, spun down, or deleted as needed.

**Note:** Interacting with a virtual machine may not be like actually remotely controlling the whole operating system — it could also be interacting with something like a web server or a mail server that has been virtualized.

#### Examples of Type-1 Hypervisors:
- VMware ESXi  
- Microsoft Hyper-V  
- Proxmox

---

[TYPW-1 Virtalization]![Screenshot 2025-06-03 124547](https://github.com/user-attachments/assets/29077a81-59d9-4193-823e-9568489912cf)
**Virtualization Explained by Andrew Bellini**

# 🛡️ Cybersecurity Home Lab (Offense & Defense)

A complete, step-by-step guide to building a secure, isolated home lab for both Red Team (offensive) and Blue Team (defensive) cybersecurity practice.

---

## 📘 Table of Contents

1. [🎯 Objectives](#objectives)  
2. [💡 Why Build a Home Lab?](#why-build-a-home-lab)  
3. [🛠️ Requirements](#requirements)  
   - [Hardware](#hardware)  
   - [Network](#network)  
   - [Software & Tools](#software--tools)  
4. [🧱 Step-by-Step Setup](#step-by-step-setup)  
   - [1. Planning & Budgeting](#1-planning--budgeting)  
   - [2. Choose Your Hypervisor & Host](#2-choose-your-hypervisor--host)  
   - [3. Design Network Architecture](#3-design-network-architecture)  
   - [4. Deploy Core VMs](#4-deploy-core-vms)  
   - [5. Build the Red Team Environment](#5-build-the-red-team-environment)  
   - [6. Build the Blue Team Environment](#6-build-the-blue-team-environment)  
   - [7. Simulate Attacks & Monitor](#7-simulate-attacks--monitor)  
   - [8. Detection, Response & Automation](#8-detection-response--automation)  
5. [🔐 Security Best Practices](#security-best-practices)  
6. [📚 Learning Resources](#learning-resources)  
7. [🧩 Next Steps](#next-steps)  

---

## 🎯 Objectives

- Practice offensive tactics: reconnaissance, exploitation, post-exploitation  
- Implement defensive strategies: network monitoring, SIEM integration, incident response  
- Combine attack, detection & response workflows end-to-end  
- Build a documented, portfolio-ready lab setup  

---

## 💡 Why Build a Home Lab?

- Gain realistic, hands-on cybersecurity skills in a controlled environment  
- Safely analyze malware, test payloads, and study detection patterns  
- Simulate enterprise-style environments (Active Directory, VLANs, DMZs)  
- Enhance both Red Team and Blue Team capabilities simultaneously  

---

## 🛠️ Requirements

### 🔧 Hardware

- Host machine: ≥ Intel i5 / Ryzen 5, 16 GB RAM, 250 GB SSD (500 GB+ preferred)  
- Optional: dedicated mini-PC, Intel NUC, or repurposed laptop  
- Network: Gigabit switch, spare router or mini firewall  

### 🌐 Network

- Isolate lab and home networks using VLANs or separate router  
- Use pfSense or similar to segment and manage traffic between zones  

### 🧰 Software & Tools

- **Hypervisor**: VMware Workstation/ESXi, Proxmox, VirtualBox, or Hyper-V  
- **Operating Systems**: Windows Server, Windows Client, Ubuntu/Debian, Kali Linux  
- **Red Team Tools**: Metasploit, msfvenom, Caldera, Nmap, OpenVAS  
- **Blue Team Tools**: pfSense/OPNsense, Suricata/Snort, ELK stack, Wazuh, Security Onion, Splunk, Sysmon  
- **Vulnerable VMs**: Metasploitable, DVWA, OWASP Broken Web App, Damn Vulnerable Linux  

---

## 🧱 Step-by-Step Setup

### 1. Planning & Budgeting

- Define goals (e.g. penetration testing, threat detection, DFIR)  
- Estimate budget for hardware, networking gear, and optional licenses  
- Consider start-up and expansion costs  

### 2. Choose Your Hypervisor & Host

- Decide between local virtualization (e.g. VirtualBox, VMware) vs bare-metal (Proxmox, ESXi)  
- Ensure virtualization is enabled (VT-x/AMD-V)  
- Configure the host with sufficient CPU, RAM, storage, and snapshots/backups  

### 3. Design Network Architecture

- Set up VLANs or separate subnets: LAB vs HOME  
- Create network segments: External (internet), DMZ (C2 servers), Internal (active directory, endpoints)  
- Place pfSense as gateway/firewall controlling traffic across segments  

### 4. Deploy Core VMs

- **Domain Controller**: Windows Server with AD & DNS  
- **SIEM**: Wazuh or ELK stack on Linux host  
- **Firewall**: pfSense VM managing lab/home networks  

### 5. Build the Red Team Environment

- Install Kali Linux with tools like Metasploit, Nmap  
- Deploy Caldera C2 server for automated adversary simulation  
- Spin up vulnerable hosts (DVWA, Metasploitable, etc.) in lab internal network  

### 6. Build the Blue Team Environment

- Install Suricata/Snort on pfSense or dedicated VM  
- Deploy centralized logging: Wazuh, Security Onion, or Splunk  
- Configure agents (Windows/Linux) for log forwarding  

### 7. Simulate Attacks & Monitor

- Use msfvenom to craft payloads targeting internal Windows VM  
- Launch adversarial campaigns via Caldera  
- Ensure alerts are generated and indexed in your SIEM console  

### 8. Detection, Response & Automation

- Develop detection rules and dashboards in SIEM (e.g., Wazuh alerts, Splunk queries)  
- Automate responses: block malicious IPs via pfSense DHCP, firewall rules, scripts  
- Conduct DFIR drills: analyze logs, trace attacks, document findings  

---

## 🔐 Security Best Practices

- Keep lab fully segregated—never mix with personal devices  
- Regularly patch and snapshot VMs, especially those exposed to attacks  
- Use strong, unique credentials and enable disk encryption where possible  
- Maintain thorough documentation: network diagrams, configurations, and labs  

---

## 📚 Learning Resources

- Red Team / Blue Team guides and tutorials  
- Reddit blue team home-lab series  
- In-depth blog posts on lab architecture and tool setup  
- Hands‑on video walkthroughs (YouTube/NID courses)  
- Community projects, vulnerable VM repositories, open threat simulation frameworks  

---

## 🧩 Next Steps

- Add diagrams (e.g., draw.io, Lucidchart) and infrastructure maps  
- Embed config snippets for Suricata, Wazuh, Caldera, etc.  
- Track progress via commits, notes on detection rules, incident write‑ups  
- Expand lab: cloud integration, ransomware simulation, IoT, routers, automation  

---

*Happy hacking and defending! Feel free to customize any section or ask for deeper config samples.*
