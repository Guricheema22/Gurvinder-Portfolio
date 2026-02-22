# 🎫 Ticket-Driven User Onboarding Lab (Jira + Microsoft Graph PowerShell)

## 📌 Lab Overview

This lab demonstrates my ability to:

- Handle IT service requests using a structured ticketing workflow (Jira simulation)
- Assign and manage ticket lifecycle
- Verify HR approval before provisioning
- Provision users using Microsoft Graph PowerShell
- Implement group-based licensing
- Validate results in Microsoft Entra ID
- Document and close tickets professionally

This simulates a real-world MSP / IT Support Level 1 / Level 2 environment.

---

# 🏢 Scenario

**Department:** HR  
**Request Type:** New User Onboarding  
**Priority:** Medium  
**License Model:** Group-Based Licensing  
**Target Group:** Finance-Users  

HR submitted a request to onboard four new Finance team members.

---

# 🎫 Jira Ticket Simulation

## 📝 Ticket Description

> Please onboard our new staff members and add them to Finance Group.
>
> - Ricky Smith  
> - Isa Guha  
> - Rohit Singh  
> - Russel Critch  

---

# 🔄 Ticket Workflow Execution

| Stage | Action Performed |
|--------|------------------|
| Open | Ticket created with Medium priority |
| Assignment | Assigned ticket to myself |
| Internal Note | Added note: "Verified HR approval. Processing with account creation via Entra ID." |
| In Progress | Connected to Microsoft Graph |
| Implementation | Created users via PowerShell |
| Access Assignment | Added users to Finance-Users security group |
| Verification | Confirmed users in Entra ID |
| Validation | Confirmed group membership in Finance-Users |
| Resolved | Updated ticket with completion notes |

---

# ⚙️ Technical Implementation

## 🔐 Step 1 – Connect to Microsoft Graph

```powershell
Connect-MgGraph -Scopes "User.ReadWrite.All","Group.ReadWrite.All","Directory.ReadWrite.All"
```

---

## 👥 Step 2 – Retrieve Finance Group ID (Dynamic Method)

```powershell
$financeGroupId = (Get-MgGroup -Filter "displayName eq 'Finance-Users'").Id
```

Using dynamic retrieval prevents hardcoding and supports production-ready scripting practices.

---

## 👤 Step 3 – Create Users and Add to Group

```powershell
$names = @(
    "Ricky Smith",
    "Isa Guha",
    "Rohit Singh",
    "Russel Critch"
)

foreach ($name in $names) {

    $first = $name.Split(" ")[0].ToLower()
    $last = $name.Split(" ")[1].ToLower()
    $upn = "$first.$last@identityonly.onmicrosoft.com"

    $user = New-MgUser `
        -DisplayName $name `
        -UserPrincipalName $upn `
        -MailNickname "$first.$last" `
        -AccountEnabled:$true `
        -PasswordProfile @{
            Password = "Temp@1234!"
            ForceChangePasswordNextSignIn = $true
        }

    New-MgGroupMember `
        -GroupId $financeGroupId `
        -DirectoryObjectId $user.Id
}
```

---

# 🎯 Group-Based Licensing Model

The **Finance-Users** security group has Microsoft 365 licenses assigned.

By adding users to this group:

- Microsoft 365 license assigned automatically
- Exchange mailbox provisioned
- Teams access enabled
- SharePoint access inherited
- Centralized license management maintained

This follows Microsoft identity and access management best practices.

---

# ✅ Verification Steps

## 🔍 Verified in Entra ID – Users Tab

Confirmed all four users were successfully created and visible in Microsoft Entra ID under **Users**.

## 🔍 Verified in Entra ID – Groups

Confirmed all four users appear under:

**Groups → Finance-Users → Members**

## 🔍 PowerShell Verification

```powershell
Get-MgGroupMember -GroupId $financeGroupId
```

All four users returned successfully.

---

# 📸 Evidence / Screenshots Included

The following screenshots are included in this repository as proof of execution:

1. Jira ticket created with Medium priority
2. Ticket assigned to myself
3. Internal note added:
   > "Verified HR approval. Processing with account creation via Entra ID."
4. PowerShell window showing:
   - Graph connection
   - User creation
   - Group membership assignment
5. Entra ID – Users tab showing new accounts
6. Entra ID – Finance-Users group showing members
7. Jira ticket marked as Resolved with completion notes

---

# 📝 Ticket Closure Comment

> All four users successfully created in Entra ID.  
> Users added to Finance-Users security group.  
> Licensing applied via group-based licensing model.  
> HR notified and temporary credentials provided securely.  
> Ticket resolved.

---

# 🧠 Skills Demonstrated

- IT Service Management (ITSM) Workflow
- Jira Ticket Handling
- Ticket Ownership & Documentation
- HR Approval Verification Process
- Microsoft Entra ID Administration
- Microsoft Graph PowerShell
- Bulk User Provisioning
- Group-Based License Management
- Validation & Post-Implementation Checks
- Secure Operational Practices
- End-to-End Ticket Lifecycle Management

---

# 🚀 Real-World Readiness

This lab demonstrates my ability to:

- Translate business requests into technical actions
- Follow structured MSP ticketing workflow
- Avoid manual portal-only processes
- Automate onboarding using PowerShell
- Verify and document changes before closure
- Maintain security and compliance practices

---

# 🔐 Security & Best Practices Applied

- Temporary password forces reset at first login
- No hardcoded group IDs (dynamic retrieval used)
- Scoped Graph permissions
- Verified approval before provisioning
- Verified post-implementation results
- Proper ticket documentation before resolution

---

# 📁 Technologies Used

- Microsoft Entra ID
- Microsoft Graph PowerShell SDK
- Jira (Trial Simulation)
- Windows PowerShell 5.1

---

# 👤 Author

**Your Name**  
IT Support | Cloud Administration | Identity & Access Management  
Aspiring Cloud / Identity Engineer
