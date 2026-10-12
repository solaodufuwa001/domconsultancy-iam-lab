# Group-Based Access Control Testing

## 1. Overview

This lab demonstrates how NTFS permissions and Active Directory security groups can be used to control access to business resources.

A Finance test resource was created on `DOM-DC01`. Access was assigned to the `DomConsultancy-Finance` security group, and inherited permissions for the general `Users` group were removed from the test folder.

The Windows **Effective Access** feature was used to evaluate the permissions available to Alice Johnson and Sarah Williams.

### Lab Environment

| Setting | Value |
|---|---|
| Domain | `domconsultancy.local` |
| Domain Controller | `DOM-DC01` |
| Test Folder | `C:\Finance-Resources` |
| Test File | `Finance-Confidential.txt` |
| Finance Group | `DomConsultancy-Finance` |
| IT Support Group | `DomConsultancy-IT-Support` |

---

## 2. Create the Finance Test Resource

A dedicated folder named `Finance-Resources` was created on the C: drive of the domain controller.

The folder contains a text file named `Finance-Confidential.txt`, which serves as the sample resource for this exercise.

### Resource Structure

```text
C:\
└── Finance-Resources
    └── Finance-Confidential.txt
```

### Evidence 01 — Finance Test Resource Created

![Evidence 01 - Finance Resource Created](../screenshots/Evidence-01-Finance-Resource-Created.png)

**Evidence description:** Shows the Finance test folder and its sample text file on the domain controller.

---

## 3. Configure NTFS Permissions for the Finance Group

NTFS permissions were configured on `C:\Finance-Resources` to grant the `DomConsultancy-Finance` security group access to the Finance test resource.

The Finance group was assigned permissions to read and write the resource. Full Control was not granted to the Finance group.

### Finance Group Permissions

| Permission | Configuration |
|---|---|
| Read | Allowed |
| Read & execute | Allowed |
| List folder contents | Allowed |
| Write | Allowed |
| Full Control | Not granted |
| Delete permissions | Not granted as a specific permission |

The permissions were configured to support the Finance resource access test while avoiding unnecessary administrative privileges.

### Evidence 02 — Finance Group NTFS Permissions

![Evidence 02 - Finance Group NTFS Permissions](../screenshots/Evidence-02-Finance-Group-NTFS-Permissions.png)

**Evidence description:** Shows the NTFS permission configuration for the `DomConsultancy-Finance` group.

---

## 4. Remove Unnecessary Inherited Permissions

The folder initially inherited permissions from its parent directory, including entries for the general `Users` group.

To make the test resource more restrictive, inheritance was disabled on `C:\Finance-Resources`, and the inherited permissions were converted to explicit permissions. The unnecessary `Users` entries were then removed from this folder.

The following entries were retained:

| Principal | Permission |
|---|---|
| `DomConsultancy-Finance` | Read, write and execute permissions |
| `Administrators` | Full Control |
| `SYSTEM` | Full Control |
| `CREATOR OWNER` | Full Control for applicable subfolders and files created by the owner |

This configuration limits access through the general `Users` entries while preserving administrative and system access.

**Security note:** Removing inherited permissions from this folder affects the folder's access control list. It does not automatically change permissions elsewhere in the domain.

### Evidence 03 — Finance Resource Group Isolation

![Evidence 03 - Finance Resource Group Isolation](../screenshots/Evidence-03-Finance-Resource-Group-Isolation.png)

**Evidence description:** Shows the Advanced Security Settings for the Finance resource after inheritance was disabled and the unnecessary `Users` entries were removed.

---

## 5. Evaluate Alice Johnson's Finance Access

Alice Johnson is a standard domain user and a member of the `DomConsultancy-Finance` security group.

Windows **Effective Access** was used to evaluate the permissions available to Alice on `C:\Finance-Resources`. The `DomConsultancy-Finance` group was included in the group-membership calculation.

The evaluation showed that Alice had the expected read and write permissions through the Finance group, without Full Control.

### Alice's Effective Access Results

| Access Check | Result |
|---|---|
| Traverse folder / execute file | Allowed |
| List folder / read data | Allowed |
| Read attributes | Allowed |
| Read extended attributes | Allowed |
| Create files / write data | Allowed |
| Create folders / append data | Allowed |
| Write attributes | Allowed |
| Write extended attributes | Allowed |
| Full Control | Not allowed |
| Delete subfolders and files | Not allowed |

These results demonstrate how permissions assigned to a security group can provide a standard user with access to a resource without granting administrative control.

### Evidence 04 — Alice Finance Effective Access

![Evidence 04 - Alice Finance Effective Access](../screenshots/Evidence-04-Alice-Finance-Effective-Access.png)

**Evidence description:** Shows the Effective Access evaluation for Alice Johnson with the `DomConsultancy-Finance` group included in the calculation.

---

## 6. Evaluate Sarah Williams's Finance Access

Sarah Williams is a standard domain user and a member of the `DomConsultancy-IT-Support` security group.

Effective Access was evaluated for Sarah on `C:\Finance-Resources`. The Finance group was not added to the group-membership calculation for this evaluation.

The evaluation showed that the permissions checked for Sarah were denied under the evaluated configuration.

This demonstrates the intended separation between Finance and IT Support access: membership of the IT Support group does not, by itself, grant access through the Finance group's permissions.

### Sarah's Effective Access Results

| Access Check | Result |
|---|---|
| Traverse folder / execute file | Denied |
| List folder / read data | Denied |
| Read data | Denied |
| Write data | Denied |
| Full Control | Denied |

**Important:** This is an Effective Access calculation, not a successful or unsuccessful interactive sign-in test or a live file-access test from a separate workstation.

### Evidence 05 — Sarah Finance Access Denied

![Evidence 05 - Sarah Finance Access Denied](../screenshots/Evidence-05-Sarah-Finance-Access-Denied.png)

**Evidence description:** Shows the Effective Access evaluation for Sarah Williams, with no Finance group added to the calculation and the evaluated permissions denied.

---

## 7. Results and Observations

The group-based access control exercise demonstrated the following:

- A dedicated Finance resource was created on the domain controller.
- NTFS permissions were assigned to the `DomConsultancy-Finance` security group.
- Unnecessary inherited permissions for the general `Users` group were removed from the test folder.
- Alice's Effective Access evaluation showed read and write permissions through the Finance group.
- Sarah's Effective Access evaluation showed the checked permissions were denied under the evaluated configuration.
- Full Control was not granted to the Finance group.
- Administrative and system permissions were retained.

The results support the principle of granting access according to business responsibilities rather than giving every user the same permissions.

### Limitations

Windows Effective Access calculates the permissions available to a selected user based on the security information included in the evaluation. It does not replace a real access test performed while signed in as that user.

A separate domain-joined client workstation will be used in a later stage to test resource access in a more realistic end-user environment. Normal interactive sign-in for standard users was not enabled on the domain controller because domain controllers should not be used as ordinary user workstations.

---

## 8. IAM and Security Relevance

This exercise demonstrates several important Identity and Access Management (IAM) principles.

### Role-Based Access Control

Permissions were assigned to the `DomConsultancy-Finance` security group rather than configured separately for each Finance user. Users can receive the appropriate permissions through group membership.

### Least Privilege

The Finance group received the permissions needed for the test resource without receiving Full Control. Administrative permissions remained separate from ordinary business access.

### Separation of Duties

Finance and IT Support were represented by separate security groups. This supports a model in which users receive access based on their responsibilities.

### Access Governance

Group membership and NTFS permissions provide two important areas to review during access reviews. When a user's responsibilities change, their group membership and resulting resource permissions should be reviewed.

### Defence in Depth

Access control should not rely on group membership alone. Effective permissions also depend on NTFS access control entries, inheritance, other group memberships and applicable deny permissions.

---

## 9. Relevance to the Hybrid IAM Project

This exercise forms part of the DomConsultancy hybrid identity lab.

The on-premises Active Directory environment provides the foundation for managing domain identities and access to local resources.

The planned hybrid identity architecture is:

```text
On-Premises Active Directory
            |
            v
      Users and Groups
            |
            v
 Microsoft Entra Connect
            |
            v
    Microsoft Entra ID
            |
            v
  Hybrid Identity Management
```

The next stages will explore identity synchronization and the relationship between on-premises Active Directory and Microsoft Entra ID.

Creating users with similar names in both environments does not automatically establish synchronization. Identity matching and synchronization will need to be configured and validated as part of the later hybrid identity stages.

---

## 10. Result

**Status: Completed — Effective Access evaluation**

The Finance resource and its NTFS permissions were configured, unnecessary inherited `Users` permissions were removed from the test folder, and Effective Access was evaluated for Alice Johnson and Sarah Williams.

The results demonstrated how Active Directory security group membership can be used to provide role-based access to a business resource while limiting unnecessary privileges.


