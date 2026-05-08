# Windows Admin Commands Cheat Sheet

A practical reference of essential Windows administrative commands used in MSP, hospital, and corporate IT environments.  
Includes system diagnostics, networking, user management, and troubleshooting tools commonly used by IT technicians.

---

## 🔧 System Information & Diagnostics
- **systeminfo** — Displays OS version, build, uptime, and hardware info  
- **wmic cpu get name** — Shows CPU model  
- **wmic logicaldisk get size,freespace,caption** — Disk usage  
- **sfc /scannow** — Scans and repairs system files  
- **DISM /Online /Cleanup-Image /RestoreHealth** — Repairs Windows image

---

## 🌐 Networking Commands
- **ipconfig /all** — Full network configuration  
- **ipconfig /flushdns** — Clears DNS cache  
- **ping <address>** — Tests connectivity  
- **tracert <address>** — Traces route to destination  
- **netstat -ano** — Shows active connections + ports  
- **nslookup <domain>** — DNS lookup

---

## 🧩 User & Permission Management
- **net user** — Lists local users  
- **net user <username> <password>** — Resets password  
- **net localgroup administrators <user> /add** — Adds user to local admins  
- **whoami /groups** — Shows group membership  
- **icacls <file>** — View/modify file permissions

---

## 🗂 File & Directory Operations
- **dir** — List files  
- **mkdir <folder>** — Create folder  
- **copy <source> <destination>** — Copy files  
- **move <source> <destination>** — Move files  
- **del <file>** — Delete file

---

## 🖥 Task & Service Management
- **tasklist** — Shows running processes  
- **taskkill /IM <process> /F** — Force kill process  
- **services.msc** — Opens Services console  
- **sc query** — Query service status  
- **eventvwr** — Opens Event Viewer

---

## 🛠 Troubleshooting Essentials
- **chkdsk /f** — Fix disk errors  
- **gpupdate /force** — Force Group Policy update  
- **gpresult /r** — Shows applied GPOs  
- **powershell** — Opens PowerShell  
- **msconfig** — Boot and startup configuration

---

## 📌 Notes
This cheat sheet is part of the **IT-PROJECTS** repository and reflects real tools used in MSP, hospital, and enterprise IT environments.
