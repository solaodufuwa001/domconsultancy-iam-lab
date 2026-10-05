# Create the Users OU

## Objective

Create a dedicated Organisational Unit for DomConsultancy user accounts.

## Configuration

A `Users` Organisational Unit was created inside the `DomConsultancy` root OU.

The structure is:

```text
domconsultancy.local
└── DomConsultancy
    └── Users
```

## Configuration

The `Users` OU was created using **Active Directory Users and Computers**.

The **Protect container from accidental deletion** option was left enabled to reduce the risk of accidental deletion of the OU.

The `Users` OU will be used to organise standard DomConsultancy user accounts separately from:

- Security groups
- Computer accounts
- Administrative accounts

This separation provides a structured foundation for future access control and Group Policy management.

## IAM and Security Relevance

Creating dedicated OUs supports **Identity and Access Management (IAM)** by providing logical boundaries for Active Directory objects.

The `Users` OU can later be used to:

- Apply user-specific Group Policy settings
- Separate standard users from administrative accounts
- Support delegated administration
- Organise users according to organisational requirements
- Apply security controls consistently

The OU itself does **not** grant permissions. Access control will be implemented separately through security groups, Group Policy, and appropriate administrative permissions.

## Evidence

**Evidence 31 — Users OU**

The screenshot confirms that the `Users` OU was successfully created inside the `DomConsultancy` root OU.

<img width="1402" height="676" alt="image" src="https://github.com/user-attachments/assets/8529cb2a-9ab7-40aa-ba43-909d65608063" />
