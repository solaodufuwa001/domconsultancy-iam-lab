# Task 4 — Role-Based Access Control

## Objective

Understand and implement role-based administrative access using Microsoft Entra ID.

## Scenario

DomConsultancy requires an IT Support Analyst to manage user accounts without providing unrestricted Global Administrator privileges.

## Test User

| Field | Value |
|---|---|
| Name | Sarah Williams |
| Department | IT |
| Job title | IT Support Analyst |
| Administrative role | User Administrator |
| Global Administrator | No |

## Security Principle — Least Privilege

The User Administrator role was assigned instead of Global Administrator to follow the principle of least privilege.

Sarah receives the administrative permissions required for her IT Support Analyst responsibilities without unnecessary elevated privileges.

## Evidence 04 — Sarah Williams User

<img width="690" height="430" alt="Screenshot 2026-09-30 083531" src="https://github.com/user-attachments/assets/e1f11f7e-d7c9-4e31-8056-7f471fc7ca63" />


## Evidence 05 — User Administrator Role Assignment

<img width="754" height="332" alt="Screenshot 2026-09-30 083503" src="https://github.com/user-attachments/assets/c14884a0-eb33-49fd-8fea-ad87cf183473" />

---

## RBAC Test 1 — User Management Access

Sarah Williams was signed in using a separate test account assigned the Microsoft Entra User Administrator role.

Sarah was able to access the Users management area and view the option to create a new user.

**Result: Passed** — The assigned role provides user-management capabilities.

### Evidence 06 — User Administrator Access

<img width="739" height="432" alt="Screenshot 2026-09-30 084628" src="https://github.com/user-attachments/assets/2fb229b3-a976-4a6a-ae77-f3fa5a82876a" />

---

## RBAC Test 2 — Privileged Role Boundary

While signed in as Sarah Williams, who has the User Administrator role, the Global Administrator role was accessed.

The Add assignments option was greyed out, preventing Sarah from assigning the Global Administrator role.

**Result: Passed** — Sarah's permissions are restricted according to her assigned administrative role.

### Evidence 07 — Global Administrator Assignment Restricted

<img width="757" height="401" alt="Screenshot 2026-09-30 085335" src="https://github.com/user-attachments/assets/4388cc38-8f2b-4c79-80e3-6fb75000849d" />


---

## RBAC Test 3 — Create User

While signed in as Sarah Williams, assigned the Microsoft Entra User Administrator role, a new test user, David Brown, was created successfully.

**Result: Passed** — Sarah's assigned role allows her to create and manage users.

### Evidence 08 — User Administrator Creates User

<img width="822" height="384" alt="Screenshot 2026-09-30 121330" src="https://github.com/user-attachments/assets/ceaf85ba-b4aa-40ef-bcd2-af2955c66342" />

---

## RBAC Test 4 — Administrative Role Protection

While signed in as Sarah Williams, the Global Administrator account was opened and its assigned roles were reviewed.

The role-assignment controls were greyed out, preventing Sarah from modifying the administrator's privileged roles.

**Result: Passed** — Sarah's User Administrator permissions do not provide the ability to modify privileged role assignments.

### Evidence 09 — Privileged Role Assignment Restricted

<img width="826" height="410" alt="Screenshot 2026-09-30 121935" src="https://github.com/user-attachments/assets/a724897c-6b7f-498c-b423-114b98b2968c" />

---

## RBAC Test 5 — Password Reset

A password-reset scenario was tested using the fictional David Brown account.

While signed in as Sarah Williams, the User Administrator role provided access to the password-reset function.

**Scenario:** An employee has forgotten their password and contacts IT Support.

**Result: Passed** — Sarah can perform the password-reset function required for the support scenario.

### Evidence 10 — User Administrator Password Reset

<img width="827" height="497" alt="Screenshot 2026-09-30 130631" src="https://github.com/user-attachments/assets/6099e9f2-9436-49ed-b0de-f0a67709d3b5" />


---

## RBAC Test 6 — User Deletion

While signed in as Sarah Williams, the User Administrator role allowed access to the Delete user function.

David Brown, a fictional test account created for the lab, was deleted to validate the administrative permission.

**Result: Passed** — The User Administrator role provides the required user-deletion capability.

### Evidence 11 — User Deletion

<img width="819" height="116" alt="Screenshot 2026-09-30 131207" src="https://github.com/user-attachments/assets/ca2f7c9c-65aa-4c17-a39c-3aaa5553420e" />


---

## RBAC Test Summary

| Test | Expected | Actual |
|---|---|---|
| Access Users | Allowed | Allowed |
| Create user | Allowed | Allowed |
| Edit user | Allowed | Allowed |
| Reset password | Allowed | Allowed |
| Delete user | Allowed | Allowed |
| Manage Global Admin | Restricted | Restricted |
| Modify privileged role assignments | Restricted | Restricted |

## Key IAM Principles Demonstrated

### Least Privilege

Give an identity only the permissions necessary to perform its responsibilities.

Sarah Williams was assigned User Administrator rather than Global Administrator.

### Role-Based Access Control

Assign permissions based on the user's job role rather than giving every administrator the same level of access.

In this scenario, Sarah is an IT Support Analyst, so her administrative permissions are focused on user management rather than unrestricted control of the Entra tenant.

## Outcome

The RBAC tests successfully demonstrated that Sarah could perform the user-management tasks required for her role while being prevented from managing privileged Global Administrator assignments.
