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

![Virtualization Explained](![Screenshot 2025-06-03 121810](https://github.com/user-attachments/assets/5eae74d5-7dca-4c2f-b8f1-54f27af93c48)
)  
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

![End Illustration](![Screenshot 2025-06-03 124547](https://github.com/user-attachments/assets/29077a81-59d9-4193-823e-9568489912cf)
)
**Virtualization Explained by Andrew Bellini**
