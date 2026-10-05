# Domain Controller Deployment

This section documents the deployment of the first Windows Server Domain Controller for the DomConsultancy Active Directory lab.

The objective is to install Active Directory Domain Services (AD DS), create the Active Directory domain, promote `DOM-DC01` to a Domain Controller, and verify that Active Directory and DNS are functioning correctly.

## Lab Server

| Setting | Value |
|---|---|
| Server Name | `DOM-DC01` |
| Operating System | Windows Server 2025 Standard Evaluation |
| Installation | Desktop Experience |
| IP Address | `10.0.2.10` |
| Network | VirtualBox NAT |
| Domain Controller | First Domain Controller |
| Organisation | DomConsultancy |

## Objectives

The following activities will be completed:

1. Install the Active Directory Domain Services (AD DS) server role.
2. Configure `DOM-DC01` as the first Domain Controller.
3. Create the Active Directory domain.
4. Configure and verify Active Directory-integrated DNS.
5. Restart and verify the Domain Controller.
6. Confirm that Active Directory Users and Computers is available.
7. Verify basic Domain Controller functionality.

## Task Documentation

| Task | Description |
|---|---|
| [01 - AD DS Installation](./01-adds-installation.md) | Install the Active Directory Domain Services role. |
| [02 - Domain Creation](./02-domain-creation.md) | Create the Active Directory domain and promote `DOM-DC01` to a Domain Controller. |
| [03 - Domain Controller Verification](./03-domain-controller-verification.md) | Verify the Domain Controller and Active Directory functionality. |
| [04 - DNS Verification](./04-dns-verification.md) | Verify Active Directory DNS configuration and name resolution. |

## Evidence

Screenshots are embedded within the relevant task documentation to show the configuration and verification performed during the lab.

## Expected Outcome

At the end of this section, `DOM-DC01` will operate as the first Domain Controller for the DomConsultancy Active Directory environment, providing:

- Active Directory Domain Services
- Active Directory-integrated DNS
- Domain authentication
- Centralised identity management
- The foundation for subsequent users, groups, Organizational Units and Group Policy configuration
