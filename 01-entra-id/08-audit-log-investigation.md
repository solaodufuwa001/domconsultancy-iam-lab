# Task 8 — Audit Log Investigation

## Objective

Investigate administrative and identity-management activities recorded in Microsoft Entra audit logs.

---

# Test 1 — User Creation Audit Investigation

## Scenario

Investigate whether the creation of a new user was recorded in the Microsoft Entra audit logs and identify the administrator responsible for the action.

## Investigation

| Field | Finding |
|---|---|
| Activity | Add user |
| Category | UserManagement |
| Status | Success |
| Initiated by | Sarah Williams |
| Target | David Brown |
| Date/time | 30 September 2026, 12:12 PM |

## Finding

The Microsoft Entra audit log confirmed that Sarah Williams successfully created the David Brown test account.

The event identified Sarah Williams as the initiating user and David Brown as the target account.

## Security Significance

Audit logs provide accountability for identity-management activities.

They allow administrators and security analysts to determine:

- Who performed an administrative action
- What action was performed
- When the action occurred
- Which identity was affected

## Evidence 22 — User Creation Audit Event

<img width="831" height="482" alt="Screenshot 2026-10-01 094715" src="https://github.com/user-attachments/assets/1f3bd1b4-d818-4813-8d72-b3302dc19edc" />


---

# Test 2 — Password Reset Audit Investigation

## Scenario

Verify that an administrator-initiated password reset performed during the RBAC testing was recorded in the Microsoft Entra audit logs.

## Finding

The Microsoft Entra audit log recorded a successful administrator-initiated password reset for David Brown.

This confirms that the password-reset action performed during the RBAC test was successfully logged.

## Security Significance

Password resets are security-sensitive identity-management activities.

Recording these actions in the audit log provides an accountability trail that can be reviewed during security investigations or access-management reviews.

## Evidence 23 — Password Reset Audit Event

<img width="804" height="249" alt="Screenshot 2026-10-01 093637" src="https://github.com/user-attachments/assets/230ee6bd-3b11-4e11-818f-f84b0f86dcba" />


---

# Test 3 — Group Membership Change

## Scenario

Investigate an identity-access change and determine which user was added to which security group.

## Investigation

| Field | Finding |
|---|---|
| Activity | Add member to group |
| Category | GroupManagement |
| Status | Success |
| Target user | Sarah Williams |
| Target group | DomConsultancy-Finance |
| Date/time | 1 October 2026, 10:12 AM |

## Finding

Microsoft Entra Audit Logs confirmed that Sarah Williams was successfully added to the **DomConsultancy-Finance** security group.

The **Modified Properties** section identified the affected group as **DomConsultancy-Finance**.

## Security Significance

Group membership changes can affect a user's access to organisational resources.

Audit logs provide visibility into these changes and allow administrators to investigate:

- Who was added to a group
- Which group was affected
- When the change occurred
- Whether the operation was successful

## Evidence 24 — Sarah Added to Finance Group

The audit event provides evidence through the following fields:

- **Activity** — Shows the action performed and its success status.

<img width="832" height="475" alt="Screenshot 2026-10-01 101443" src="https://github.com/user-attachments/assets/528d87c4-8dd0-47f0-93ce-539cb2b825cb" />
  
- **Target(s)** — Shows Sarah Williams and the affected group.

<img width="375" height="338" alt="Screenshot 2026-10-01 101534" src="https://github.com/user-attachments/assets/99b7d462-797f-4db8-89d5-836788ea2513" />

  
- **Modified Properties** — Confirms the affected group as DomConsultancy-Finance.

<img width="388" height="289" alt="Screenshot 2026-10-01 144732" src="https://github.com/user-attachments/assets/6cb4ad6a-b18e-40d1-aa0a-afd41c7e3d77" />

---

# Audit Investigation Outcome

The audit log investigations demonstrated that Microsoft Entra records important identity-management activities and provides an accountability trail for administrative actions.

The investigation covered:

- User creation
- Password reset
- Group membership changes

These logs can support security investigations, access reviews, incident response and administrative accountability.
