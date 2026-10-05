## 4. Organisational Units

Organisational Units (OUs) are used to logically organise users, computers, groups, and other Active Directory objects.

The lab will create an OU structure for **DomConsultancy** to demonstrate:

- Logical organisation of Active Directory objects
- Delegation of administration
- Group Policy targeting
- Separation of users, computers, and administrative accounts
- Least-privilege administration

### Planned OU Structure

```text
domconsultancy.local
└── DomConsultancy
    ├── Users
    ├── Groups
    ├── Computers
    └── IT-Admins
