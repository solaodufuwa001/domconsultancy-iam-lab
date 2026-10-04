# Task 5 — Group-Based Access Control

## Objective

Create departmental security groups to organise users according to their department and establish a scalable foundation for group-based access control.

## Departmental Security Groups

| Group | Department | Members |
|---|---|---|
| DomConsultancy-Finance | Finance | Alice Johnson |
| DomConsultancy-HR | HR | David Brown |
| DomConsultancy-IT | IT | Sarah Williams |

## Security Principle

Department-based security groups provide a scalable method of managing access.

Rather than assigning permissions individually to each employee, access can be assigned to a group and users can inherit access through group membership.

This approach simplifies access management and makes it easier to manage permissions as the organisation grows.

## Evidence 12 — HR Security Group

<img width="813" height="436" alt="Screenshot 2026-09-30 135155" src="https://github.com/user-attachments/assets/071f55e7-b05f-4176-ae0f-4ae45b9d622d" />

## Evidence 13 — IT Security Group

<img width="819" height="453" alt="Screenshot 2026-09-30 135549" src="https://github.com/user-attachments/assets/61f9b391-35d3-4365-a006-dfc2b360ae46" />


---

## Multiple Group Membership

### Scenario

An IT Support Analyst requires additional access to Finance resources to support the Finance department.

### Action

Sarah Williams was added to the **DomConsultancy-Finance** security group while remaining a member of **DomConsultancy-IT**.

### Result

Sarah is now a member of two security groups, demonstrating how group membership can be used to provide additional access based on business responsibilities.

This demonstrates that access can be extended through group membership without changing Sarah's underlying administrative role.

## Evidence 14 — Multiple Group Membership

<img width="735" height="399" alt="Screenshot 2026-09-30 143344" src="https://github.com/user-attachments/assets/81b42ae0-811d-4ee4-8652-37d22132c61c" />


## IAM Concept Demonstrated

Group membership can be used to provide access according to business responsibilities while keeping administrative roles separate from resource access.

In this scenario:

- **DomConsultancy-IT** provides Sarah's departmental membership.
- **DomConsultancy-Finance** provides additional Finance-related access.
- Sarah's **User Administrator** role remains separate from these group memberships.
