# Active Directory Lab

This section documents the design, deployment and configuration of the DomConsultancy Active Directory environment using Windows Server 2025 and Microsoft Active Directory Domain Services (AD DS).

The lab is designed to provide practical, hands-on experience with identity and access management in a Windows Server environment.

## Lab Objectives

The Active Directory lab covers:

- Windows Server deployment and configuration
- Active Directory Domain Services (AD DS)
- Domain Controller deployment
- Active Directory Users and Computers
- Organisational Units (OUs)
- Users and security groups
- Group Policy
- Access control and permissions
- Authentication and authorisation
- DNS integration with Active Directory
- Testing and verification of identity and access controls

## Lab Structure

| Section | Description |
|---|---|
| [01 - Lab Environment](./01-lab-environment.md) | Windows Server virtual machine deployment and initial lab environment configuration. |
| [02 - Server Configuration](./02-server-configuration.md) | Server naming, static IP configuration, DNS troubleshooting, Windows updates and time zone configuration. |
| [03 - Domain Controller](./03-domain-controller/) | Installation and configuration of Active Directory Domain Services and deployment of the first Domain Controller. |

## Lab Environment

| Component | Configuration |
|---|---|
| Virtualisation Platform | Oracle VirtualBox |
| Operating System | Windows Server 2025 Standard Evaluation |
| Server Name | `DOM-DC01` |
| Organisation | DomConsultancy |
| Network | VirtualBox NAT |
| Static IPv4 Address | `10.0.2.10` |

## Evidence

Evidence screenshots are included within the relevant documentation sections to demonstrate configuration changes, troubleshooting activities and verification results.

## Progress

- [x] Windows Server lab environment created
- [x] Server configured and renamed to `DOM-DC01`
- [x] Static IPv4 configuration completed
- [x] DNS troubleshooting and resolution completed
- [x] Windows security updates applied
- [x] Server time zone configured
- [ ] Active Directory Domain Services installed
- [ ] Domain Controller deployed
- [ ] Active Directory DNS verified
- [ ] Active Directory users and groups configured
- [ ] Group Policy configured
- [ ] Access and authentication testing completed

## Next Steps

The next stage is to install Active Directory Domain Services and promote `DOM-DC01` to the first Domain Controller for the DomConsultancy Active Directory environment.
