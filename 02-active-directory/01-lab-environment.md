<img width="535" height="465" alt="Screenshot 2026-10-04 174256" src="https://github.com/user-attachments/assets/d54febe3-6ac6-423d-bb0d-0c4d6c30c643" /><img width="535" height="465" alt="Screenshot 2026-10-04 174256" src="https://github.com/user-attachments/assets/f50b286b-a8de-4f39-8535-09cb3cd83416" /># Task 1 — Active Directory Lab Environment

## Objective

Build the Windows Server environment that will be used as the foundation of the DomConsultancy Active Directory lab.

The objective of this task was to:

- Create a dedicated Windows Server virtual machine
- Configure the virtual hardware
- Install Windows Server 2025
- Configure the local Administrator account
- Verify that Windows Server is operational
- Prepare the server for the installation of Active Directory Domain Services (AD DS)

---

## Lab Environment

| Component | Configuration |
|---|---|
| Organisation | DomConsultancy |
| Virtualisation Platform | Oracle VirtualBox |
| Server Name | DomConsultancy-DC01 |
| Operating System | Windows Server 2025 |
| Edition | Standard Evaluation |
| Installation Type | Desktop Experience |
| CPU | 2 vCPUs |
| RAM | 4 GB |
| Virtual Disk | 60 GB |
| Disk Type | VDI |
| Disk Allocation | Dynamically Allocated |
| Network | NAT |
| Firmware | EFI Disabled |
| Intended Role | Active Directory Domain Controller |

---

## 1. Virtual Machine Creation

A dedicated virtual machine named `DomConsultancy-DC01` was created in Oracle VirtualBox for the Active Directory lab.

### Virtual Machine Configuration

- **Name:** DomConsultancy-DC01
- **Operating System:** Windows Server 2025 (64-bit)
- **Memory:** 4096 MB
- **Processors:** 2
- **Virtual Disk:** 60 GB
- **Disk Type:** VDI
- **Storage Allocation:** Dynamically allocated
- **Network Adapter:** NAT
- **Virtual Cable:** Connected
- **EFI:** Disabled

The virtual machine was configured with sufficient resources for the planned Active Directory lab.

### Evidence

**Evidence 01 — DomConsultancy-DC01 Virtual Machine Configuration**

Screenshot showing the VirtualBox configuration for the Windows Server virtual machine.

<img width="535" height="465" alt="Screenshot 2026-10-04 174256" src="https://github.com/user-attachments/assets/b4ca150d-9976-44f8-af2f-86e57c1154b2" />

---

## 2. Windows Server Installation Media

The first ISO downloaded was identified as the Windows Server Languages and Optional Features package rather than the operating system installation media.

The incorrect ISO was not suitable for booting the Windows Server installation environment.

The correct Windows Server 2025 Evaluation ISO was subsequently downloaded from Microsoft.

The correct installation media was identified by the filename containing:

`SERVER_EVAL_x64FRE_en-us.iso`

The correct ISO was then attached to the `DomConsultancy-DC01` virtual machine.

### Troubleshooting

The initial boot attempt resulted in a **No bootable medium found** message.

Investigation of the ISO filename identified that the wrong installation media had been downloaded.

The issue was resolved by obtaining the correct Windows Server 2025 Evaluation ISO.

### Evidence

The corrected ISO successfully booted into Windows Server Setup.

---

## 3. Windows Server 2025 Setup

The virtual machine successfully booted from the Windows Server 2025 Evaluation ISO.

The Windows Server Setup environment was displayed.

### Language Configuration

The following settings were used:

- **Language to install:** English (United States)
- **Time and currency format:** English (United States)

### Evidence

**Evidence 02 — Windows Server 2025 Setup**

Screenshot showing the Windows Server Setup language configuration screen.

<img width="522" height="430" alt="Screenshot 2026-10-04 174634" src="https://github.com/user-attachments/assets/a1c51f9f-8b12-427d-9b9e-1c91970ac5e7" />

---

## 4. Windows Server Edition Selection

The following operating system edition was selected:

**Windows Server 2025 Standard Evaluation (Desktop Experience)**

Desktop Experience was selected because the graphical interface provides a practical environment for learning and administering Active Directory.

The Standard edition is sufficient for the DomConsultancy training environment.

### Evidence

**Evidence 03 — Windows Server Edition**

Screenshot showing the selected Windows Server 2025 Standard Evaluation (Desktop Experience) edition.

<img width="509" height="419" alt="Screenshot 2026-10-04 174743" src="https://github.com/user-attachments/assets/df8a79df-c6e4-4d09-9f51-89a430d1d101" />


---

## 5. Virtual Disk Configuration

Windows Server Setup detected the configured 60 GB virtual disk.

The installation target was:

| Disk | Size | Status |
|---|---:|---|
| Disk 0 | 60 GB | Unallocated |

Because this was a new virtual machine, the disk was left as unallocated space.

Windows Setup was allowed to automatically create the required system partitions.

No existing partitions or data needed to be preserved.

### Evidence

**Evidence 04 — Windows Server Disk Selection**

Screenshot showing the 60 GB Disk 0 as unallocated installation space.

<img width="521" height="420" alt="Screenshot 2026-10-04 175018" src="https://github.com/user-attachments/assets/1b30e4c8-e8c6-4d25-ab5e-e1a1542251c0" />


---

## 6. Installation Confirmation

Before installation, Windows Server Setup displayed the selected configuration:

- Windows Server 2025 Standard Evaluation
- Desktop Experience
- Keep nothing

The configuration was reviewed and confirmed before proceeding.

### Evidence

**Evidence 05 — Windows Server Ready to Install**

Screenshot showing the final Windows Server installation configuration.

<img width="558" height="447" alt="Screenshot 2026-10-04 175102" src="https://github.com/user-attachments/assets/a60e81a9-a45c-40e3-8068-c13c0ba3afa3" />


---

## 7. Windows Server Installation

Windows Server 2025 was installed onto the 60 GB virtual disk.

The installation process copied the operating system files to the virtual disk and automatically created the required system partitions.

The virtual machine restarted automatically during the installation process.

### Evidence

**Evidence 06 — Windows Server Installation**

Screenshot showing Windows Server 2025 actively installing.

<img width="523" height="441" alt="Screenshot 2026-10-04 175323" src="https://github.com/user-attachments/assets/90f90507-26f0-4e87-9678-54ad1780f7dc" />


---

## 8. Local Administrator Configuration

After the operating system installation completed, Windows Server prompted for configuration of the built-in local Administrator account.

The default username was:

`Administrator`

A strong password was created for the lab environment.

The Administrator password is not stored in this repository.

### Security Consideration

Credentials are treated as sensitive information and are not stored in GitHub, screenshots, documentation or source-control files.

### Evidence

**Evidence 07 — Server Administrator Configuration**

Screenshot showing the Windows Server Administrator account configuration screen.

<img width="530" height="425" alt="Screenshot 2026-10-04 181024" src="https://github.com/user-attachments/assets/63021765-f613-4bd5-bea8-c38c459f0306" />


---

## 9. Initial Windows Server Login

The Windows Server installation completed successfully and the server reached the Windows Server login screen.

The local Administrator account was used to access the server.

### Evidence

**Evidence 08 — Windows Server 2025 Initial Login**

Screenshot showing the Windows Server 2025 login screen.

<img width="510" height="421" alt="Screenshot 2026-10-04 184434" src="https://github.com/user-attachments/assets/61126701-f46b-4cc8-b197-ed664d01646b" />

---

## 10. Server Manager Verification

After successful authentication, Windows Server opened **Server Manager**.

Server Manager confirmed that the local Windows Server installation was operational and ready for additional server-role configuration.

At this stage, Active Directory Domain Services had not yet been installed.

### Evidence

**Evidence 09 — Windows Server 2025 Server Manager**

Screenshot showing Server Manager running successfully on `DomConsultancy-DC01`.

<img width="512" height="421" alt="Screenshot 2026-10-04 182400" src="https://github.com/user-attachments/assets/bf3b827b-a859-4550-b208-06581a6832da" />


---

# Security Considerations

The lab is being built as an isolated training environment to demonstrate enterprise Identity and Access Management concepts.

The following security principles were considered during the initial build:

- Least privilege
- Separation of administrative responsibilities
- Secure credential handling
- Controlled virtualisation environment
- Dedicated test identities
- Avoidance of real production credentials

Sensitive credentials are not stored in the public GitHub repository.

---

# Current Status

### Completed

- [x] Oracle VirtualBox environment prepared
- [x] DomConsultancy-DC01 virtual machine created
- [x] Virtual hardware configured
- [x] 60 GB virtual disk configured
- [x] NAT networking configured
- [x] Correct Windows Server 2025 Evaluation ISO obtained
- [x] Windows Server 2025 Standard Evaluation installed
- [x] Desktop Experience installed
- [x] Local Administrator account configured
- [x] Windows Server login verified
- [x] Server Manager verified

### Next Steps

- [ ] Configure server identity
- [ ] Configure static IP address
- [ ] Configure network settings
- [ ] Install Active Directory Domain Services
- [ ] Promote the server to a Domain Controller
- [ ] Create the DomConsultancy Active Directory domain
- [ ] Create Organisational Units
- [ ] Create users and security groups
- [ ] Configure Group Policy
- [ ] Test domain authentication and access

---

# Conclusion

The Windows Server 2025 foundation for the DomConsultancy Active Directory lab has been successfully deployed.

The `DomConsultancy-DC01` virtual machine is operational and ready for the next stage of the lab: configuring the server for Active Directory Domain Services.
