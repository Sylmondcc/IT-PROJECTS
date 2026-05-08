# Active Directory Lab – Users and Groups

This section documents how users, groups, and Organizational Units (OUs) are created and managed in a typical MSP/hospital/corporate IT environment.

---

## Organizational Unit (OU) Structure

A clean OU structure makes AD easier to manage and apply Group Policies.

Recommended structure:

lab.local
│
├── _Admins
├── _Workstations
├── _Servers
└── _Users


---

## Creating Users

### **Method 1 — Active Directory Users and Computers (ADUC)**

1. Open **ADUC**
2. Navigate to **_Users** OU
3. Right‑click → **New → User**
4. Fill in:
   - First Name  
   - Last Name  
   - User Logon Name (e.g., jdoe)
5. Set password
6. Uncheck “User must change password at next logon” (lab only)

### **Method 2 — PowerShell**

New-ADUser -Name "John Doe" -GivenName "John" -Surname "Doe" -SamAccountName "jdoe" -UserPrincipalName "jdoe@lab.local" -Path "OU=_Users,DC=lab,DC=local" -AccountPassword (Read-Host -AsSecureString "Password") -Enabled $true

---

## 👥 Creating Groups

### **Group Types**
- **Security Groups** — used for permissions  
- **Distribution Groups** — used for email (not needed in this lab)

### **Group Scopes**
- **Global** — best for users  
- **Domain Local** — best for assigning permissions  
- **Universal** — multi-domain environments

### **Create a Security Group (GUI)**

1. In ADUC, right‑click **_Users** OU  
2. Select **New → Group**  
3. Name:  
   Helpdesk
4. Group Scope: **Global**  
5. Group Type: **Security**

### **Create a Security Group (PowerShell)**

New-ADGroup -Name "Helpdesk" -GroupScope Global -GroupCategory Security -Path "OU=_Users,DC=lab,DC=local"

---

## ➕ Adding Users to Groups

### **GUI Method**
1. Open the user (e.g., jdoe)  
2. Go to **Member Of**  
3. Click **Add**  
4. Enter group name (e.g., Helpdesk)

### **PowerShell Method**

Add-ADGroupMember -Identity "Helpdesk" -Members "jdoe"

---

## Permissions Basics (Real MSP/Hospital Practice)

### **Rule #1 — Assign permissions to groups, not users**
Never give direct permissions to a user account.

### **Rule #2 — Use the AGDLP model**

Accounts → Global Groups → Domain Local Groups → Permissions

### **Rule #3 — Keep OUs clean**
Workstations, servers, and users should NEVER be mixed.

---

## 📌 Notes

This file is part of the **Active Directory Lab** in the IT-PROJECTS repository.  
It reflects identity management practices used in MSP, hospital, and enterprise IT environments.

