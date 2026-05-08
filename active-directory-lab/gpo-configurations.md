
# Active Directory Lab – Full Documentation (Users, Groups, and GPOs)

This document combines all identity and policy management steps for MSP, hospital, and corporate IT environments.

---

# 🗂 Organizational Unit (OU) Structure

A clean OU structure makes AD easier to manage and apply Group Policies.

Recommended structure:

lab.local
│
├── _Admins
├── _Workstations
├── _Servers
└── _Users

**Why this matters:**  
Hospitals, MSPs, and enterprises rely on OUs to apply GPOs cleanly and avoid chaos.

---

# 👤 Creating Users

## Method 1 — Active Directory Users and Computers (ADUC)

1. Open **ADUC**
2. Navigate to **_Users** OU
3. Right‑click → **New → User**
4. Fill in:
   - First Name  
   - Last Name  
   - User Logon Name (e.g., jdoe)
5. Set password
6. Uncheck “User must change password at next logon” (lab only)

## Method 2 — PowerShell

New-ADUser -Name "John Doe" -GivenName "John" -Surname "Doe" -SamAccountName "jdoe" -UserPrincipalName "jdoe@lab.local" -Path "OU=_Users,DC=lab,DC=local" -AccountPassword (Read-Host -AsSecureString "Password") -Enabled $true

---

# 👥 Creating Groups

## Group Types
- **Security Groups** — used for permissions  
- **Distribution Groups** — used for email (not needed in this lab)

## Group Scopes
- **Global** — best for users  
- **Domain Local** — best for assigning permissions  
- **Universal** — multi-domain environments

## Create a Security Group (GUI)

1. In ADUC, right‑click **_Users** OU  
2. Select **New → Group**  
3. Name:  
   Helpdesk
4. Group Scope: **Global**  
5. Group Type: **Security**

## Create a Security Group (PowerShell)

New-ADGroup -Name "Helpdesk" -GroupScope Global -GroupCategory Security -Path "OU=_Users,DC=lab,DC=local"

---

# ➕ Adding Users to Groups

## GUI Method
1. Open the user (e.g., jdoe)  
2. Go to **Member Of**  
3. Click **Add**  
4. Enter group name (e.g., Helpdesk)

## PowerShell Method

Add-ADGroupMember -Identity "Helpdesk" -Members "jdoe"

---

# 🔐 Permissions Best Practices (Real MSP/Hospital Standards)

### Rule #1 — Assign permissions to groups, not users  
Never give direct permissions to a user account.

### Rule #2 — Use the AGDLP model  
Accounts → Global Groups → Domain Local Groups → Permissions

### Rule #3 — Keep OUs clean  
Workstations, servers, and users should NEVER be mixed.

---

# 🧠 What is a GPO?

A **Group Policy Object (GPO)** is a set of rules that control settings on computers and users in an Active Directory domain.

Used for:

- Security hardening  
- Password policies  
- Software restrictions  
- Login banners  
- Drive mappings  
- Windows Update settings  

---

# 🏛 Creating a New GPO

## Method 1 — Group Policy Management Console (GPMC)

1. Open **Group Policy Management**
2. Right‑click the OU (e.g., _Workstations)
3. Select **Create a GPO in this domain, and Link it here**
4. Name the GPO (example: Workstation Security Policy)
5. Right‑click the GPO → **Edit**

## Method 2 — PowerShell

New-GPO -Name "Workstation Security Policy"
New-GPLink -Name "Workstation Security Policy" -Target "OU=_Workstations,DC=lab,DC=local"

---

# 🔐 Common Real-World GPOs

## 1. Password & Account Lockout Policy  
Linked at the **domain level**.

Path:
Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies

---

## 2. Disable USB Storage  
Path:
Computer Configuration → Administrative Templates → System → Removable Storage Access

Set:
All Removable Storage classes: Deny all access → Enabled

---

## 3. Login Banner (Legal Notice)  
Path:
Computer Configuration → Windows Settings → Security Settings → Local Policies → Security Options

---

## 4. Map Network Drives  
Path:
User Configuration → Preferences → Windows Settings → Drive Maps

Example:
Drive Letter: H:  
Path: \\dc01\shared

---

## 5. Windows Update Settings  
Path:
Computer Configuration → Administrative Templates → Windows Components → Windows Update

---

# 🧪 Testing GPOs

## Force GPO Update
gpupdate /force

## Check Applied GPOs
gpresult /r

## Generate HTML Report
gpresult /h report.html

---

# 📌 Notes

This file entails of  identity and policy management used in MSP, hospital, and enterprise IT environments.
