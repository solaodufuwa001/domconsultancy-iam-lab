# 01 - Microsoft Entra ID

## Objective

Build a foundational understanding of Microsoft Entra ID and implement core Identity and Access Management controls within the DomConsultancy environment.

## Lab Environment

| Component | Configuration |
|---|---|
| Organisation | DomConsultancy |
| Identity Platform | Microsoft Entra ID |
| Licence | Microsoft Entra ID Free |
| Environment | IAM Training / Test Lab |

## Technologies

- Microsoft Entra ID
- Microsoft Entra users and groups
- Microsoft Entra administrative roles
- Microsoft Entra RBAC
- Multi-Factor Authentication (MFA)
- Security Defaults
- Sign-in Logs
- Audit Logs
- Conditional Access
- Authentication Strengths
- Named Locations

## Lab Tasks

| Task | Area | Documentation |
|---|---|---|
| 1 | Lab Environment | [View Task](01-lab-environment.md) |
| 2 | Create Test User | [View Task](02-create-test-user.md) |
| 3 | Security Groups | [View Task](03-security-groups.md) |
| 4 | RBAC & Least Privilege | [View Task](04-rbac-least-privilege.md) |
| 5 | Group-Based Access | [View Task](05-group-based-access.md) |
| 6 | Security Defaults & MFA | [View Task](06-mfa-security-defaults.md) |
| 7 | Sign-in Log Investigation | [View Task](07-sign-in-log-investigation.md) |
| 8 | Audit Log Investigation | [View Task](08-audit-log-investigation.md) |
| 9 | Conditional Access | [View Task](09-conditional-access.md) |

## Key IAM Concepts

- Identity and Access Management (IAM)
- Role-Based Access Control (RBAC)
- Least Privilege
- Group-Based Access Control
- Multi-Factor Authentication
- Authentication Monitoring
- Auditability
- Conditional Access
- Identity Security

## Investigation & Testing

The lab included practical testing and investigation of:

- Administrative role boundaries
- User creation and management
- Password reset
- User deletion
- Multiple group membership
- MFA registration and authentication challenges
- Successful sign-in events
- Failed authentication events
- Sign-in error code 50126
- IP-based location information
- Device information
- User creation audit events
- Password reset audit events
- Group membership audit events

## Conditional Access

Conditional Access concepts, authentication strengths and Named Locations were explored.

The DomConsultancy lab uses Microsoft Entra ID Free, which limited the ability to create and enforce the full Conditional Access policies required for the exercise. The available Conditional Access configuration areas were therefore investigated and documented.

## Security Principles Demonstrated

### Least Privilege

Administrative permissions were limited according to job responsibilities rather than providing unrestricted Global Administrator access.

### Role-Based Access Control

Administrative permissions were assigned according to the user's role.

### Group-Based Access Control

Security groups were used to organise users according to department and business responsibilities.

### Multi-Factor Authentication

MFA was registered and tested using Microsoft Authenticator.

### Identity Monitoring

Sign-in and audit logs were investigated to understand authentication activity and administrative changes.

### Accountability

Audit logs were used to identify who performed identity-management actions, what action was performed, when it occurred and which identity was affected.

## Status

**Completed**
