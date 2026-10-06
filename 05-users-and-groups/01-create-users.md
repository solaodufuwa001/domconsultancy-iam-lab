# Create Users

## 1. Create Alice Johnson

A test user account named **Alice Johnson** was created in the on-premises Active Directory environment.

The account was created inside the dedicated `Users` OU within the `DomConsultancy` organisational structure.

### User Configuration

| Setting | Value |
|---|---|
| Full Name | Alice Johnson |
| Username | `alice.johnson` |
| UPN | `alice.johnson@domconsultancy.local` |
| Domain | `domconsultancy.local` |
| OU | `DomConsultancy/Users` |
| Account Type | Standard User |

The account was configured to require the user to change the administrator-provided password at the next logon.

This demonstrates a basic identity lifecycle process in which an administrator creates an account while ensuring the initial password is not retained permanently.

---

## 2. Active Directory Location

The account was created at:

```text
domconsultancy.local
└── DomConsultancy
    └── Users
        └── Alice Johnson
```

Placing users inside a dedicated OU provides a structured location where user-specific Group Policy and administrative controls can later be applied.

---

## 3. Hybrid IAM Relevance

Alice Johnson already exists as a test identity in the Microsoft Entra ID portion of this lab.

The on-premises Active Directory account created here is currently a separate identity.

### On-Premises Active Directory Identity

`alice.johnson@domconsultancy.local`

### Microsoft Entra ID Identity

Alice Johnson exists in the cloud tenant using the tenant's `onmicrosoft.com` domain.

The identities are intentionally separate at this stage.

Later in the hybrid IAM section, Microsoft Entra integration will be used to demonstrate how an on-premises Active Directory identity can be synchronised with a cloud identity.

This creates a practical identity lifecycle across both on-premises and cloud environments.

---

## 4. Security Considerations

The Alice Johnson account was created as a standard user rather than an administrator.

The account was configured with:

- A unique username
- An initial password
- Mandatory password change at first logon
- Placement within the dedicated `Users` OU
- No administrative privileges

Following the principle of least privilege, administrative permissions will be assigned separately through appropriate security groups and administrative accounts.

---

## Evidence

### Evidence 03 — Alice Johnson User Confirmation

<img width="413" height="249" alt="Screenshot 2026-10-06 164951" src="https://github.com/user-attachments/assets/bac9ebfe-b1f4-4ca9-b33e-af4e754bb4c5" />


The screenshot shows the account details before creation, including:

- Full name: Alice Johnson
- UPN: `alice.johnson@domconsultancy.local`
- Requirement to change the password at next logon
- Creation location: `domconsultancy.local/DomConsultancy/Users`

### Evidence 04 — Alice Johnson Created

<img width="425" height="262" alt="Screenshot 2026-10-06 165219" src="https://github.com/user-attachments/assets/d8ae9d31-170e-4840-b438-d3afbb93893d" />


The screenshot confirms that Alice Johnson was successfully created inside:

```text
domconsultancy.local
└── DomConsultancy
    └── Users
        └── Alice Johnson
```

---

## Result

The on-premises Active Directory user account for Alice Johnson was successfully created.

# 3. Create Sarah Williams

Sarah Williams represents an IT Support Analyst within DomConsultancy.

Sarah provides a second standard user identity for demonstrating role separation and group-based access control.

## User Configuration

| Setting | Value |
|---|---|
| **First Name** | Sarah |
| **Last Name** | Williams |
| **Full Name** | Sarah Williams |
| **Username** | `sarah.williams` |
| **UPN** | `sarah.williams@domconsultancy.local` |
| **Pre-Windows 2000 Logon** | `DOMCONSULTANCY\sarah.williams` |
| **Account Type** | Standard User |
| **OU Location** | `DomConsultancy/Users` |

The account was configured with **User must change password at next logon** enabled.

Password information is not documented in this portfolio for security reasons.

## Active Directory Location

Sarah Williams was created inside:

`domconsultancy.local → DomConsultancy → Users`

This maintains consistent identity organisation within the Active Directory environment.

## Evidence

### Evidence 05 — Sarah Williams AD Identity

The New User window shows the identity information configured for Sarah Williams.

![Sarah Williams AD Identity](../screenshots/Evidence-05-Sarah-Williams-AD-Identity.png)

### Evidence 06 — Sarah Password Policy

The password configuration stage shows the account password settings. The password itself is intentionally not documented.

![Sarah Password Policy](../screenshots/Evidence-06-Sarah-Password-Policy.png)

### Evidence 07 — Sarah User Confirmation

The final user creation confirmation shows the configured Sarah Williams account before creation.

![Sarah User Confirmation](../screenshots/Evidence-07-Sarah-User-Confirmation.png)

### Evidence 08 — Sarah Williams Created

The Active Directory Users and Computers console confirms that Sarah Williams was successfully created inside the dedicated Users OU.

![Sarah Williams Created](../screenshots/Evidence-08-Sarah-Williams-Created.png)

---

# 4. User Role Separation

The two standard users represent different business functions within DomConsultancy.

| User | Business Role | AD Account Type |
|---|---|---|
| Alice Johnson | Finance Analyst | Standard User |
| Sarah Williams | IT Support Analyst | Standard User |

The users are intentionally kept as standard accounts. Business access is subsequently managed through security-group membership.

This supports:

- Role-based access control
- Least privilege
- Separation of responsibilities
- Centralised access management
- Easier user onboarding and offboarding

The corresponding security groups are documented separately in:

`02-create-security-groups.md`

---

# 5. IAM and Least-Privilege Relevance

Creating users as standard accounts establishes a secure identity baseline.

Neither Alice nor Sarah is granted unnecessary administrative privileges at account creation.

Instead, access is assigned according to business responsibilities through security groups:

**Alice Johnson → DomConsultancy-Finance**

**Sarah Williams → DomConsultancy-IT-Support**

This approach reduces the need to assign permissions directly to individual users and provides a more scalable access-management model.

---

# 6. Hybrid Identity Relevance

These Active Directory identities form part of the on-premises identity foundation for the wider hybrid IAM lab.

The planned architecture is:

**Active Directory → Users & Security Groups → Microsoft Entra Connect → Microsoft Entra ID → Hybrid Identity**

The on-premises identities intentionally use the internal domain:

- `alice.johnson@domconsultancy.local`
- `sarah.williams@domconsultancy.local`

The existing Microsoft Entra environment contains the corresponding Alice Johnson cloud identity. The later hybrid identity phase will demonstrate how on-premises identities can be synchronised and represented in Microsoft Entra ID.

Creating the identities separately at this stage allows the synchronization and identity-matching process to be demonstrated rather than assuming that similarly named accounts are automatically connected.

---

# 7. Security Considerations

The following security practices were applied during user creation:

- Standard user accounts were used instead of unnecessary administrative accounts.
- Users were placed in a dedicated Users OU.
- Passwords are not recorded in the public repository.
- Users are required to change their password at first logon.
- Access is intended to be managed through security groups.
- Finance and IT Support responsibilities are separated.
- Administrative privileges will only be introduced where required for a specific lab scenario.

---

# Result

Two standard Active Directory identities have been successfully created:

- **Alice Johnson** — Finance Analyst
- **Sarah Williams** — IT Support Analyst

Both accounts are located in:

`domconsultancy.local → DomConsultancy → Users`

The identities are now ready for group-based access control and subsequent IAM testing.

The next stage is to use the security groups to control access based on each user's business role.

The account is now available for subsequent IAM exercises involving:

- Security group membership
- Access control
- Group Policy
- Authentication testing
- Identity lifecycle management
- Hybrid identity synchronisation

This establishes the first user identity within the on-premises Active Directory environment that will later be incorporated into the hybrid IAM architecture.
