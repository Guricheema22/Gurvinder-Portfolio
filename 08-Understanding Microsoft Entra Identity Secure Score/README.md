# 🔐Lab - 08 Understanding Microsoft Entra **Identity Secure Score**

Microsoft Entra **Identity Secure Score** is a built-in security analytics tool that measures how well an organisation is protecting its identities in the cloud. It provides a **percentage score** based on recommended identity security best practices.

This README explains what the score is, why it matters, and how following Microsoft recommendations can improve overall cloud security.

---

## ⭐ What Is Identity Secure Score?

Identity Secure Score is essentially a **security report card** for your Entra ID environment.

It analyses your tenant configuration and gives you a score based on:
- Authentication methods  
- Multifactor authentication (MFA) usage  
- Password protection  
- Privileged role management  
- Conditional Access posture  
- Legacy authentication  
- Risk-based protections  

A higher score means stronger protection against account compromise and identity-based attacks.

---

## 📊 How Secure Score Works

Microsoft provides a list of **recommended improvements**, each with a point value.

You increase your Secure Score when you complete recommendations such as:
- Enabling MFA for all users  
- Requiring registration for Self-Service Password Reset (SSPR)  
- Blocking insecure legacy protocols (POP, IMAP, SMTP AUTH)  
- Reducing the number of Global Administrators  
- Enforcing password protection policies  
- Configuring Conditional Access policies  
- Enabling sign-in risk detection  

You *do not lose points* for not completing an action — but completing more actions increases your overall security maturity.

---

## 🧩 Examples of Recommendations That Improve Secure Score

These actions are commonly used to harden identity security:

### ✔ MFA Enforcement  
Protects accounts from phishing, credential stuffing, and password spray attacks.

### ✔ SSPR Registration  
Allows users to reset their passwords securely without contacting IT.

### ✔ Block Legacy Authentication  
Legacy protocols cannot enforce MFA and are a major attack vector.

### ✔ Limit High-Privilege Roles  
Reducing Global Administrators reduces risk of privilege misuse or compromise.

### ✔ Password Protection  
Using banned-password lists and modern policies improves security and user hygiene.

### ✔ Conditional Access Policies  
Applies adaptive controls such as location-based access, device checks, or risk scoring.

Each action directly contributes to a more secure identity environment.

---

## 🛡 Why Identity Secure Score Matters

Identity Secure Score:
- Highlights vulnerabilities you may miss manually  
- Prioritises improvements based on real impact  
- Helps strengthen your zero-trust posture  
- Supports audits and compliance requirements  
- Makes your cloud environment more resilient  
- Demonstrates proactive identity security to employers or clients  

A strong identity foundation leads to a more secure overall cloud environment.

---

## 📌 Summary

Identity Secure Score is one of the most valuable tools in Microsoft Entra for evaluating and improving identity security.  
By following Microsoft’s recommendations—even gradually—you significantly improve your organisation’s protection against modern identity-based threats.


Just let me know!
