# Admins OU

## Configuration

The `Admins` OU was created inside the `DomConsultancy` root OU using **Active Directory Users and Computers**.

The `Admins` OU will be used to organise administrative user accounts separately from standard user accounts.

Separating administrative identities provides a structured foundation for applying additional security controls to privileged accounts.

## IAM and Security Relevance

A dedicated administrative OU supports **privileged identity management** and the principle of **least privilege**.

It can later be used to:

- Separate administrative accounts from standard user accounts
- Apply stronger security policies to privileged accounts
- Support delegated administration
- Apply administrative account-specific Group Policy settings
- Provide clearer visibility of privileged identities

The OU itself does not grant administrative permissions. Administrative privileges should be assigned separately through appropriate security groups and role-based access controls.

## Evidence

**Evidence 34 — Admins OU**

The screenshot confirms that the `Admins` OU was successfully created inside the `DomConsultancy` root OU.

<img width="708" height="337" alt="Screenshot 2026-10-05 163611" src="https://github.com/user-attachments/assets/3c61347f-73de-4008-bf9e-28d798523f78" />


The Active Directory tree shows:

```text
domconsultancy.local
└── DomConsultancy
    ├── Users
    ├── Groups
    ├── Computers
    └── Admins
