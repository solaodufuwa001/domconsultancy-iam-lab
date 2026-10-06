# Create Security Groups

## 1. Create DomConsultancy-Finance Security Group

A security group was created in Active Directory to support group-based access control for Finance users.

The group was created with the following configuration:

| Setting | Value |
|---|---|
| **Group Name** | `DomConsultancy-Finance` |
| **Group Scope** | Global |
| **Group Type** | Security |
| **Location** | `domconsultancy.local/DomConsultancy/Groups` |

The group is intended to provide access to Finance-related resources through group membership rather than assigning permissions directly to individual users.

### Evidence

**Evidence 01 — Group Configuration**

The Active Directory New Object - Group window shows the `DomConsultancy-Finance` group configured with Global scope and Security group type.

<img width="411" height="236" alt="Screenshot 2026-10-06 172947" src="https://github.com/user-attachments/assets/26f082bd-3a45-4fa7-93b3-aac4d1f6dd9e" />

---

## 2. Finance Security Group Created

The `DomConsultancy-Finance` security group was successfully created inside the dedicated Groups OU.

### Evidence

**Evidence 02 — Finance Group Created**

The Active Directory Users and Computers console shows `DomConsultancy-Finance` inside:

`domconsultancy.local → DomConsultancy → Groups`

<img width="709" height="332" alt="Screenshot 2026-10-06 173110" src="https://github.com/user-attachments/assets/5fce847e-f4ee-4f48-b287-13e49eeb615e" />


---

## 3. Add Alice Johnson to the Finance Group

Alice Johnson was added as a member of the `DomConsultancy-Finance` security group.

This establishes a group-based access control relationship:

**Alice Johnson → DomConsultancy-Finance → Finance Resources**

Rather than assigning permissions directly to Alice, access can later be assigned to the security group. This supports the principle of managing access through groups and makes future access administration easier.

### Evidence

**Evidence 03 — Alice Johnson Group Membership**

The group membership properties show `Alice Johnson` as a member of `DomConsultancy-Finance`.

<img width="395" height="301" alt="Screenshot 2026-10-06 174649" src="https://github.com/user-attachments/assets/c3bb79f4-32de-415e-8596-adda7882302b" />

---

## 4. IAM and Least-Privilege Relevance

Security groups provide a scalable method of managing access within Active Directory.

In this lab:

- Alice Johnson is a standard user.
- Alice is not given administrative privileges.
- Finance access is associated with the `DomConsultancy-Finance` security group.
- Permissions can later be assigned to the group instead of individual users.
- Removing a user from the group can remove their associated access without modifying each resource individually.

This supports **group-based access control** and the **principle of least privilege**.

---

## 5. Hybrid Identity Relevance

The Finance security group is also part of the lab's planned hybrid identity architecture.

The intended architecture is:

**Active Directory → Users & Security Groups → Microsoft Entra Connect → Microsoft Entra ID → Hybrid Identity**

The on-premises `DomConsultancy-Finance` group provides an Active Directory identity and access-control object that can later be incorporated into the hybrid identity workflow.

The group will **not** automatically become the existing Entra `DomConsultancy-Finance` group simply because the names match. Synchronisation and identity matching will be configured and tested later as part of the hybrid identity phase.

---

## Result

The first Active Directory security group has been successfully created and populated.

**Created:**
- `DomConsultancy-Finance`

**Member:**
- `Alice Johnson`

This establishes the foundation for subsequent Active Directory access-control testing and the later hybrid identity integration with Microsoft Entra ID.
