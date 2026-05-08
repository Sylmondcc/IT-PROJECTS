**This lab covers the core Microsoft 365 admin tasks:**

---

# 1. Tenant Setup (Quick Version)

- Create a free tenant at: https://developer.microsoft.com/microsoft-365/dev-program  
- Choose **Instant Sandbox**  
- Sign in at https://admin.microsoft.com  
- Make sure you can open:
  - Admin Center
  - Entra ID
  - Exchange Admin Center
  - SharePoint Admin Center
  - Teams Admin Center
  - Intune
  - Security Portal

---

# 2. Security Defaults (MFA)

- Go to https://entra.microsoft.com  
- Identity → Protection → Security Defaults  
- Make sure **Enabled** is ON  

This enforces:
- MFA  
- Blocks legacy authentication  
- Basic identity protection  

---

# 3. Create a User

Admin Center -- Users -- Active Users -- Add a user

Fill:
- Display Name  
- Username  
- Password  

Assign:
- Microsoft 365 E5 Developer license  

This creates the user + mailbox + OneDrive.

---

# 4. Assign or Change Licenses

Users -- Active Users -- Select user -- Licenses and Apps

Turn on:
- Microsoft 365 E5 Developer  
- EMS E5  
- Windows Enterprise  

---

# 5. Create a Security Group

Teams & groups -- Active teams & groups → Add a group  
Choose **Security Group**  


