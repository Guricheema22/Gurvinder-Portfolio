# 🔐 Lab 07: Configuring & Demonstrating Self-Service Password Reset (SSPR) in Microsoft Entra ID

In this lab, I demonstrate how I configured **Self-Service Password Reset (SSPR)** for an existing security group and how an end user (**Russel Critch**) successfully reset his password using **Microsoft Authenticator (OATH TOTP)**.

This mirrors a real enterprise setup where secure password recovery reduces support tickets and improves user productivity.

---

## ✅ **Lab Objectives**
- Apply SSPR policy to an existing user group  
- Confirm users have valid authentication methods  
- Demonstrate the full “Forgot my password” experience  
- Verify successful password change  

---

## 🧩 **1. Existing Setup Overview**

Before starting this lab:

- The security group **Finance-Users** already existed  
- **Russel Critch** was already a member  
- Russel had previously set up the **Microsoft Authenticator app**

📸 **Screenshot 1 – Finance-Users group showing existing members**

This allowed the SSPR rollout without modifying group membership.

---

## 🛠️ **2. Enable SSPR for the Finance-Users Group**

### Steps:
1. Go to **Entra Admin Center → Password Reset → Properties**  
2. Configure:
   - **Self-service password reset enabled:** Selected group  
   - **Selected group:** Finance-Users

This ensures only Finance-Users are allowed to use SSPR.

📸 **Screenshot 2 – SSPR Properties showing Finance-Users assigned**

---

## 🔐 **3. Verify Russel’s Authentication Method**

Before testing SSPR, I confirmed that Russel already had a valid authentication factor registered.

### Steps:
1. Go to **Users → Russel Critch**  
2. Open **Authentication Methods**  
3. Confirm **Software OATH token / Authenticator App** is listed

📸 **Screenshot 3 – Russel’s authentication methods showing Software OATH token**

This ensures he can verify his identity when resetting his password.

---

## 🧪 **4. Demonstrate SSPR Password Reset**

I performed the reset from the user perspective.

### Steps:
1. Navigate to **login.microsoftonline.com**  
2. Enter Russel’s username  
3. Select **Forgot my password**  
4. SSPR validates:
   - Russel is in the **Finance-Users** group  
5. He is prompted to verify through **Authenticator app verification code**  
6. Enter the 6-digit code  
7. Create a new password  
8. Password reset is completed

📸 **Screenshot 4 – Identity verification using Authenticator**  
📸 **Screenshot 5 – Password reset confirmation**

---

## 🔍 **5. Verify Successful Login**

To complete the lab, I tested logging into Microsoft 365 with the new password.

📸 **Screenshot 6 – Successful login using new password**

---

# 🎉 **Lab Completed**

This lab demonstrates:

- How SSPR can be scoped to specific user groups  
- How MFA (Authenticator app) supports password recovery  
- How secure, self-service password reset works end-to-end  
- Practical identity administration skills relevant to enterprise environments  

This setup reduces dependency on IT support and improves account lifecycle security.

---
