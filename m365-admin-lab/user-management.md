# Microsoft 365 Admin Lab – 
---

# 1. Create a Free Microsoft 365 Tenant

1. Go to https://developer.microsoft.com/microsoft-365/dev-program  
2. Join the Microsoft 365 Developer Program  
3. Choose **Instant Sandbox**  
4. Microsoft gives you:
   - A tenant domain (example: contoso.onmicrosoft.com)  
   - A global admin account  
   - A temporary password  
---

# 2. Sign In to the Admin Center

1. Go to https://admin.microsoft.com  
2. Sign in with your global admin  
3. Make sure you can open:
   - Admin Center  
   - Entra ID (Azure AD)  
   - Exchange Admin Center  
   - SharePoint Admin Center  
   - Teams Admin Center  
   - Intune  
   - Security Portal  

---

# 3. Enable Security Defaults (MFA)

1. Go to https://entra.microsoft.com  
2. Identity → Protection → Security Defaults  
3. Make sure it is **Enabled**

This enforces:
- MFA  
- Blocking legacy authentication  
- Basic identity protection  

---

# 4. Create a User (Admin Center)

1. Admin Center → Users → Active Users  
2. Click **Add a user**  
3. Fill in:
   - Display Name  
   - Username  
   - Password  
4. Assign a license (E5 Developer)  
5. Finish  

---

# 5. Assign or Change Licenses

1. Users -- Active Users  
2. Select the user  
3. Click **Licenses and Apps**  
4. Turn on:
   - Microsoft 365 E5 Developer  
   - EMS E5  
   - Windows Enterprise  

Licenses activate:
- Email  
- Teams  
- OneDrive  
- SharePoint  
- Security features  

---

# 6. Create a Security Group

1. Teams & groups -- Active teams & groups  
2. Click **Add a group**  
3. Choose **Security Group**  


5. Create  

Security groups are used for permissions and access control.

---

# 7. Add Users to Groups

1. Teams & groups → Active teams & groups  
2. Select the group  
3. Members → Add members  
4. Choose the user  

used for:
- Permissions  
- Access to shared mailboxes  
- Teams membership  
- App access  

---

# 8. Assign Admin Roles

1. Users → Active Users  
2. Select a user  
3. Click **Manage roles**  
4. Choose:
- Helpdesk Admin  
- User Admin  
- Exchange Admin  
- Teams Admin  
- Global Admin (rarely used)  

---

# 9. Create a Shared Mailbox

1. Teams & groups → Shared mailboxes  
2. Click **Add a shared mailbox**  
3. Enter:
- Name  
- Email address  
4. Add members (delegates)

Shared mailboxes do **not** require a license unless:
- Over 50GB  
- Litigation hold enabled  

---

# 10. Reset a User’s Password

1. Users → Active Users  
2. Select user  
3. Click **Reset password**  
4. Choose:
- Auto-generate  
- Custom password  

---

# 11. Validation Checklist

After creating a user, verify:

- User appears in Active Users  
- License assigned  
- Mailbox created  
- OneDrive provisioned  
- Group membership correct  
- Admin roles correct  
- MFA enforced  

---

# 📌 Notes

This focuses on IT support roles. Advanced automation (PowerShell, JSON exports, Intune scripting) 
