# Microsoft 365 Admin Lab – Tenant Setup

This document outlines how to create and configure a Microsoft 365 tenant for hands‑on practice.  
It uses the free Microsoft 365 Developer Program, which provides a full E5 environment for labs.

---

## 1. Create a Free Microsoft 365 Developer Tenant

Microsoft provides a free renewable tenant with:

- 25 E5 licenses  
- Azure AD / Entra ID  
- Exchange Online  
- SharePoint / OneDrive  
- Teams  
- Intune  
- Security & Compliance Center  

### Steps: 

1. Go to: https://developer.microsoft.com/microsoft-365/dev-program  
2. Sign in with a personal Microsoft account  
3. Join the **Microsoft 365 Developer Program**  
4. Choose **Instant Sandbox**  
5. Microsoft will generate:
   - Tenant domain (e.g., *contoso.onmicrosoft.com*)  
   - Global admin account  
   - Temporary password  

Record these credentials securely.

---

## 2. Sign In to the Microsoft 365 Admin Center

1. Go to: https://admin.microsoft.com  
2. Sign in with your new global admin account  
3. Complete the first‑time setup prompts  
4. Verify access to:
   - Admin Center  
   - Azure AD / Entra  
   - Exchange Admin Center  
   - SharePoint Admin Center  
   - Security Portal  
   - Endpoint Manager (Intune)

This confirms the tenant is active.

---

## 3. Configure Basic Security Defaults

Microsoft enables **Security Defaults** by default.

To verify:

1. Go to: https://entra.microsoft.com  
2. Navigate to **Identity → Protection → Security Defaults**  
3. Ensure it is **Enabled**

Security Defaults enforces:

- MFA for admins  
- Blocking legacy authentication  
- Basic identity protection  

---

## 4. Enable MFA for the Global Admin

1. Go to: **Users -- All Users**  
2. Select your admin account  
3. Choose **Manage multifactor authentication**  
4. Enable MFA  
5. Sign out and sign back in to complete setup

This protects your tenant from unauthorized access.

---

## 5. Assign E5 Licenses

1. Go to **Users -- Active Users**  
2. Select your admin account  
3. Click **Licenses and Apps**  
4. Assign:
   - Microsoft 365 E5 Developer  
   - Enterprise Mobility + Security E5  
   - Windows 10/11 Enterprise  

This unlocks all features needed for the lab.

---

## 6. Add a Custom Domain (Optional)

If you want a more realistic environment:

1. Go to **Settings -- Domains**  
2. Click **Add Domain**  
3. Enter your domain (e.g., *labregents.com*)  
4. Add TXT record in your DNS provider  
5. Verify domain ownership

This allows custom email addresses and branding.

---

## 7. Create Organizational Structure

Recommended structure:

- **Users**
- **Admins**
- **Service Accounts**
- **Groups**
- **Devices**
- **Shared Mailboxes**

This mirrors real MSP/hospital/corporate environments.

---

## 8. Validate Tenant Health

Check:

- Admin Center loads  
- Exchange Admin Center loads  
- SharePoint Admin Center loads  
- Teams Admin Center loads  
- Intune loads  
- Security Portal loads  

If all portals open, the tenant is fully functional.

---

## 📌 Notes

This tenant is used for the Microsoft 365 Admin Lab in the IT-PROJECTS repository.  
It provides a realistic environment for identity, security, email, and device management practice.
