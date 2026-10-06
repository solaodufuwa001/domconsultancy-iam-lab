# Computers OU

## Configuration

The `Computers` OU was created inside the `DomConsultancy` root OU using **Active Directory Users and Computers**.

The `Computers` OU will be used to organise computer accounts separately from user accounts and security groups.

This provides a structured location for managing domain-joined computers and applying computer-specific security policies.

## IAM and Security Relevance

Separating computer accounts into a dedicated OU supports structured identity and device management.

The OU can later be used to:

- Apply computer-specific Group Policy settings
- Manage security configurations for domain-joined devices
- Separate computer objects from user and group objects
- Support delegated administration
- Apply security controls consistently to managed computers

The OU itself does not grant permissions. Access control and security configuration will be implemented through Group Policy, security groups, and appropriate administrative permissions.

## Evidence

**Evidence 33 — Computers OU**

The screenshot confirms that the `Computers` OU was successfully created inside the `DomConsultancy` root OU.

<img width="1408" height="676" alt="image" src="https://github.com/user-attachments/assets/d7a6b712-562a-4df7-8e94-3a05ff70dd63" />


The Active Directory tree shows:

```text
domconsultancy.local
└── DomConsultancy
    ├── Users
    ├── Groups
    └── Computers
