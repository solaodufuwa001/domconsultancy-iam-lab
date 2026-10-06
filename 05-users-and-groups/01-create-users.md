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

The account is now available for subsequent IAM exercises involving:

- Security group membership
- Access control
- Group Policy
- Authentication testing
- Identity lifecycle management
- Hybrid identity synchronisation

This establishes the first user identity within the on-premises Active Directory environment that will later be incorporated into the hybrid IAM architecture.
