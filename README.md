# Samba Enterprise Lab

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Category](https://img.shields.io/badge/Category-Enterprise%20File%20Sharing-blue)
![Samba](https://img.shields.io/badge/Samba-AD%20%7C%20Permissions%20Control-yellow)
![MultiVM](https://img.shields.io/badge/Environment-Multi--VM-blueviolet)
![RealWorld](https://img.shields.io/badge/Scenario-Enterprise%20Ready-critical)

This repository contains a complete two-part Samba lab designed to simulate how a small company would deploy and manage shared folders on a Linux server.  
It includes both a **manual Samba setup** and a fully **automated deployment** using shell scripts.

This project demonstrates:
- Linux system administration skills
- User and group management
- Permissions and access control
- Samba configuration for enterprise use cases
- Network configuration (Netplan)
- Automation scripting (Bash)
- Documentation and troubleshooting

---

## 📂 Repository Structure

```

samba-enterprise-lab/
│
├── 01-basic-samba-setup/
│   ├── configs/         # smb.conf, netplan config, users
│   ├── docs/
│   ├── screenshots/
│   └── README.md
│
└── 02-automated-samba-setup/
    ├── docs/
    ├── screenshots/
    ├── scripts/         # automation scripts for Samba deployment
    └── README.md

```

---

## 🏢 Scenario

You are working as an Internal IT Engineer for **NovaTech Enterprise**, a small company that needs two types of shared network folders:

- A **public shared folder** for all employees  
- A **team-restricted folder** (e.g., /dev or /accounting)  
- Users must authenticate through Samba  
- Access must be fully controlled via Linux groups  
- Configuration must be reliable and reproducible

The company first requests a **manual setup**, then asks you to build an **automated version**.

---

## 🧪 Lab Modules

### **Module 1 – Basic Samba Setup**
- User and group creation  
- Samba installation & configuration  
- Share creation with correct permissions  
- Network configuration (Netplan)  
- Client access testing  

### **Module 2 – Automated Samba Setup**
- Bash scripts for:
  - user creation  
  - group assignment  
  - directory creation  
  - permissions and ACLs  
  - Samba configuration deployment  
- Automated client mount logic

---

## 🎯 Skills Demonstrated
- Linux system administration  
- Samba deployment  
- File sharing architecture  
- Network configuration  
- Permission management  
- Automation scripting  
- Troubleshooting  
- Professional documentation

---

## 📌 Author
Part of my training as an Internal IT Engineer preparing to work in Japan.  
This lab reflects practical sysadmin scenarios and real company workflows.
