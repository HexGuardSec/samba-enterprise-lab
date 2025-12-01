# Basic Samba Setup

## 🎯 Objective
This module demonstrates how to manually configure Samba on an Ubuntu Server to provide shared folders for different departments in a small company.

You will:
- Install and configure Samba
- Create users and groups
- Set folder permissions and ownership
- Configure shares inside `smb.conf`
- Configure network settings using Netplan
- Test access from a Linux client

---

## 🏢 Scenario
**NovaTech Enterprise** needs two shared folders:

1. **/srv/shared** → accessible to all employees  
2. **/srv/dev** (or /accounting) → restricted to a specific team  

Employees authenticate using Samba credentials.

---

## 📌 Steps Performed

### 1. User & Group Setup
- Created groups: `employees`, `developers`  
- Added each user to the appropriate group  
- Set Samba passwords using `smbpasswd`

### 2. Folder Structure
```

/srv/shared
/srv/dev

```
Permissions:
- `shared` → group `employees`  
- `dev` → group `developers`

### 3. Samba Configuration
Edited `/etc/samba/smb.conf`:
- Workgroup, security mode
- Defined shares with proper permissions
- `valid users = @developers` for restricted share

### 4. Netplan Configuration
Configured Static IP:
```

configs/netplan.yaml

```

### 5. Testing (Kali Client)
- Listed shares
- Mounted Samba folders
- Tested read/write access
- Verified permissions

---

## 📂 Files Included
- `configs/smb.conf`  
- `configs/netplan.yaml`  
- `configs/users.txt`
- `documentation/architecture.md`
- `setup-guide.md`
- `screenshots/`

---

## 🧠 Skills Demonstrated
- Linux administration  
- Samba fundamentals  
- Group-based access control  
- Network configuration  
- Troubleshooting Samba access