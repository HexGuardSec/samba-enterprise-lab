# **Automated Samba Workstation Deployment**

This module provides an automated deployment script designed to simulate how a company prepares a new Linux workstation for an employee.
The script handles:

* User creation
* Role assignment (employee / developer / accountant)
* Samba share mounting based on the user’s role
* Basic network configuration
* Validation of connectivity (ping checks)
* Creation of local mount points and folder structure

This mirrors a real onboarding workflow often handled by Internal IT or SysAdmin teams.

---

## **📌 Features Overview**

### 🔐 **User Creation & Role Assignment**

The script automatically:

* Creates a Linux user
* Assigns the correct role using Linux groups
* Ensures consistent access logic (group-based)

Roles supported:

* `employee`
* `developer`
* `accountant`

---

### 🗂️ **Role-Based Samba Auto-Mounting**

Depending on the user’s department, only the relevant shares are mounted.

| Role       | Mounted Shares         |
| ---------- | ---------------------- |
| Employee   | `commun`               |
| Developer  | `commun`, `developer`  |
| Accountant | `commun`, `accountant` |

All mounts use:

```
noperm, uid=<user>, gid=<group>, vers=3.0
```

✔ Avoids permission mismatch
✔ Ensures correct local ownership
✔ Matches professional Samba usage

---

### 🌐 **Network Configuration (Netplan)**

The script:

* Detects the network interface
* Asks for static IP details
* Generates the Netplan configuration
* Applies it automatically

This simulates provisioning a workstation inside a company network.

---

### 📦 **Dependency Installation**

The script ensures required packages are installed:

* net-tools
* netplan.io
* curl / wget
* cifs-utils (for Samba mounting)

---

## **📂 Repository Structure**

```
02-automated-samba-setup/
│
├── scripts/
│   └── setup_user.sh
│
├── documentation/
│   ├── architecture.md
│   └── screenshots/
│
└── README.md
```

---

## **🛠️ How the Script Works**

### 1️⃣ Run the script

```
sudo bash setup_user.sh
```

### 2️⃣ Enter user information

* Username
* Password
* Role

### 3️⃣ Enter network settings

* Interface
* IP Address
* Gateway
* DNS

### 4️⃣ Enter Samba server IP

The script mounts only the relevant shares based on the role.

---

## **📂 Share Mounting Logic (Detailed)**

### Always mounted:

* `/mnt/samba/commun`

### Developer only:

* `/mnt/samba/developer`

### Accountant only:

* `/mnt/samba/accountant`

The script ensures:

* No unauthorized share is created
* Clean and predictable workstation state
* Correct group ownership matching Samba permissions

---

## **🧼 Cleanup / Reset Commands**

Unmount everything:

```
sudo umount /mnt/samba/commun 2>/dev/null
sudo umount /mnt/samba/developer 2>/dev/null
sudo umount /mnt/samba/accountant 2>/dev/null
```

Remove folders:

```
sudo rm -rf /mnt/samba/{commun,developer,accountant}
```

Remove user:

```
sudo userdel -r username
```

---

## **🎯 Objective of This Automated Lab**

This project simulates **real-world Internal IT workflows**, including:

* Workstation onboarding
* Role-based access control
* Network provisioning
* Samba mount automation
* User lifecycle management

It demonstrates core SysAdmin and IT support skills required in modern enterprise environments.