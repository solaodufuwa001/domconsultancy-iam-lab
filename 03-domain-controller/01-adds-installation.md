# Active Directory Domain Services Installation

This document records the installation of the Active Directory Domain Services (AD DS) server role on `DOM-DC01`.

The purpose of this stage is to install the AD DS role that will later be used to promote `DOM-DC01` to the first Domain Controller for the DomConsultancy Active Directory environment.

## 1. Launch Add Roles and Features Wizard

The **Add Roles and Features Wizard** was opened from Server Manager to begin the installation of the Active Directory Domain Services role.

The wizard opened on the **Before You Begin** page.

The page provides a checklist of prerequisites that should be considered before installing a server role, including:

- Administrator credentials
- Static network configuration
- Current Windows security updates

The destination server identified by the wizard was `DOM-DC01`.

The prerequisites had previously been configured and verified during the server configuration stage.

### Evidence

**Evidence 01 — AD DS Installation Wizard**

Screenshot showing the **Before You Begin** page of the Add Roles and Features Wizard with `DOM-DC01` identified as the destination server.

<img width="739" height="361" alt="Screenshot 2026-10-05 091339" src="https://github.com/user-attachments/assets/20d9bdef-a2aa-4296-b584-0f837a8dda76" />


---

## 2. Select Installation Type

The installation type was selected in the Add Roles and Features Wizard.

The **Role-based or feature-based installation** option was selected because Active Directory Domain Services is being installed as a server role on the Windows Server machine.

This installation method allows the required server role and its associated features to be installed directly on `DOM-DC01`.

### Evidence

**Evidence 02 — Installation Type**

Screenshot showing **Role-based or feature-based installation** selected in the Add Roles and Features Wizard.

<img width="746" height="360" alt="Screenshot 2026-10-05 092808" src="https://github.com/user-attachments/assets/c0812677-6d26-4abb-9819-6c513b5ec35d" />

---

## 3. Select Destination Server

The Server Selection page was used to identify the Windows Server that would receive the Active Directory Domain Services role.

The option to select a server from the server pool was used.

`DOM-DC01` was selected as the destination server.

This ensures that the AD DS role will be installed on the server that has already been prepared with the required hostname, static IP configuration, DNS connectivity, Windows updates and time zone configuration.

### Evidence

**Evidence 03 — Server Selection**

Screenshot showing `DOM-DC01` selected as the destination server for the Active Directory Domain Services installation.

<img width="741" height="361" alt="Screenshot 2026-10-05 094650" src="https://github.com/user-attachments/assets/572568ab-3381-4100-a4a6-c2e3e7643f94" />


---

## 4. Select Active Directory Domain Services

After reviewing the required features, the required management tools were accepted by selecting **Add Features**.

The wizard returned to the Server Roles page with **Active Directory Domain Services** selected.

The AD DS role is now marked for installation on `DOM-DC01`.

No additional server roles were selected at this stage.

### Evidence

**Evidence 05 — AD DS Role Selected**

Screenshot showing **Active Directory Domain Services** selected for installation on `DOM-DC01`.

<img width="746" height="364" alt="Screenshot 2026-10-05 100606" src="https://github.com/user-attachments/assets/c3ba65de-903e-4caf-a1ee-0c97743ee58f" />

<img width="741" height="362" alt="Screenshot 2026-10-05 100842" src="https://github.com/user-attachments/assets/f6175674-6020-4bac-87e7-cb5bd43ba739" />

## 5. Review Additional Features

The Features page was reviewed after selecting the Active Directory Domain Services role.

The wizard displayed the available Windows Server features that could be installed. No additional optional features were manually selected at this stage.

The **Group Policy Management** feature was already selected as part of the required Active Directory management tooling.

The default feature selections were retained to avoid installing unnecessary components.

### Evidence

**Evidence 06 — Features Selection**

Screenshot showing the Features page of the Add Roles and Features Wizard and the available feature selections for `DOM-DC01`.

<img width="741" height="362" alt="Screenshot 2026-10-05 100842" src="https://github.com/user-attachments/assets/6ba7678e-f371-4757-874b-6a933048ca8c" />

## 6. Active Directory Domain Services Information

The Active Directory Domain Services information page was reviewed before proceeding with the installation.

The page explains that Active Directory Domain Services (AD DS) stores information about users, computers and other network resources and provides centralised management of these objects.

The page also identifies DNS as a required component of an Active Directory environment. DNS is required for Active Directory services and domain controllers to locate and communicate with each other.

The wizard also recommends deploying a minimum of two Domain Controllers for production environments to provide redundancy and availability.

For this isolated lab environment, a single Domain Controller will be deployed initially to provide hands-on experience with Active Directory administration.

### Evidence

**Evidence 07 — AD DS Information**

Screenshot showing the Active Directory Domain Services information page and the requirement for DNS within an Active Directory environment.

<img width="740" height="362" alt="Screenshot 2026-10-05 125430" src="https://github.com/user-attachments/assets/df1f2ba4-99b0-4d55-885c-86d949339e34" />

## 7. Confirm AD DS Installation

The installation selections were reviewed before starting the AD DS role installation.

The confirmation page showed that the following components would be installed on `DOM-DC01`:

- Active Directory Domain Services
- Group Policy Management
- Remote Server Administration Tools
- AD DS and AD LDS Tools
- Active Directory module for Windows PowerShell
- Active Directory Administrative Center
- AD DS Snap-ins and Command-Line Tools

These management tools provide the administrative interfaces required to manage and troubleshoot the Active Directory environment.

The **Restart the destination server automatically if required** option was left unchecked so that any restart could be controlled manually.

### Evidence

**Evidence 08 — AD DS Installation Confirmation**

Screenshot showing the selected Active Directory Domain Services role and associated management tools before installation.

<img width="741" height="360" alt="Screenshot 2026-10-05 125635" src="https://github.com/user-attachments/assets/93cf9428-6889-4470-9f6a-273f5bf2a160" />

## 8. AD DS Installation Completed

The Active Directory Domain Services role installation completed successfully on `DOM-DC01`.

The Results page reported:

**"Installation succeeded on DOM-DC01."**

The wizard also indicated that additional configuration was required to make the server a Domain Controller.

A **"Promote this server to a domain controller"** link was displayed, indicating that the AD DS role had been installed successfully and that the next stage was to configure the server as a Domain Controller.

### Evidence

**Evidence 09 — AD DS Installation Success**

Screenshot showing the successful installation of Active Directory Domain Services on `DOM-DC01` and the available option to promote the server to a Domain Controller.

<img width="737" height="356" alt="Screenshot 2026-10-05 131718" src="https://github.com/user-attachments/assets/5a936193-13c4-47e3-bf9e-2cee85b94a86" />

## 9. Create a New Active Directory Forest

The Active Directory Domain Services Configuration Wizard was opened after the AD DS role was successfully installed.

Because `DOM-DC01` is the first Domain Controller in the DomConsultancy lab and there is no existing Active Directory domain, the **Add a new forest** deployment option was selected.

The root domain name was configured as:

`domconsultancy.local`

This creates a new Active Directory forest containing the first domain for the lab environment.

### Evidence

**Evidence 10 — New Forest Configuration**

Screenshot showing **Add a new forest** selected and the root domain name configured as `domconsultancy.local` for `DOM-DC01`.

<img width="717" height="368" alt="Screenshot 2026-10-05 133253" src="https://github.com/user-attachments/assets/c2ff802d-61a5-4eea-b4c0-33b2c1be3db9" />

## 10. Configure Domain Controller Options

The Domain Controller Options page was configured for the first Domain Controller in the `domconsultancy.local` forest.

The forest and domain functional levels were left at **Windows Server 2025**, matching the operating system used for the lab.

The following Domain Controller capabilities were configured:

| Setting | Configuration |
|---|---|
| Forest Functional Level | Windows Server 2025 |
| Domain Functional Level | Windows Server 2025 |
| DNS Server | Enabled |
| Global Catalog | Enabled |
| Read-Only Domain Controller | Disabled |

A Directory Services Restore Mode (DSRM) password was also configured. The password was entered and confirmed successfully.

The DSRM password is used for Active Directory recovery and maintenance operations and is not included in the GitHub documentation.

### Evidence

**Evidence 11 — Domain Controller Options**

Screenshot showing the configured forest and domain functional levels, DNS Server and Global Catalog selections, RODC disabled, and the completed DSRM password fields.

<img width="713" height="358" alt="Screenshot 2026-10-05 134014" src="https://github.com/user-attachments/assets/d56871c6-0230-47fb-a40a-7c733e0b73e2" />

## 11. DNS Options

The DNS Options page was reviewed as part of the Domain Controller promotion process.

A warning was displayed stating that a DNS delegation could not be created because the authoritative parent zone could not be found.

This is expected for the lab environment because `domconsultancy.local` is being created as a new internal Active Directory DNS namespace and there is no existing parent DNS zone requiring delegation.

The **Create DNS delegation** option was therefore left disabled.

The Domain Controller will provide the authoritative DNS service for the new `domconsultancy.local` Active Directory domain.

### Evidence

**Evidence 12 — DNS Options**

Screenshot showing the DNS Options page and the DNS delegation warning for the new `domconsultancy.local` domain.

<img width="734" height="354" alt="Screenshot 2026-10-05 134253" src="https://github.com/user-attachments/assets/16c1b2d2-58bd-4072-9ea0-bcbed6e87c6e" />

## 12. Configure NetBIOS Domain Name

The Additional Options page was reviewed during the Domain Controller promotion process.

Windows automatically generated the NetBIOS domain name:

`DOMCONSULTANCY`

This corresponds to the Active Directory DNS domain:

`domconsultancy.local`

The automatically generated NetBIOS name was retained because it provides a suitable short domain identifier for the DomConsultancy Active Directory environment.

The configuration is therefore:

| Setting | Value |
|---|---|
| DNS Domain Name | `domconsultancy.local` |
| NetBIOS Domain Name | `DOMCONSULTANCY` |

### Evidence

**Evidence 13 — NetBIOS Domain Name**

Screenshot showing the automatically generated `DOMCONSULTANCY` NetBIOS domain name for the `domconsultancy.local` Active Directory domain.

<img width="721" height="367" alt="Screenshot 2026-10-05 134723" src="https://github.com/user-attachments/assets/58704b70-4feb-4777-a1aa-344c3a25b7a5" />


## 13. Configure Active Directory Paths

The Paths page was reviewed during the Domain Controller promotion process.

The wizard defines the storage locations for the Active Directory database, log files and SYSVOL folder.

The default Windows Server paths were retained because this is a single-server laboratory environment with one virtual disk.

The configured paths are:

| Component | Location |
|---|---|
| Active Directory Database | `C:\WINDOWS\NTDS` |
| AD Log Files | `C:\WINDOWS\NTDS` |
| SYSVOL | `C:\WINDOWS\SYSVOL` |

The Active Directory database contains directory information, while the log files support database operations and recovery. The SYSVOL folder stores domain-wide files such as Group Policy data.

### Evidence

**Evidence 14 — Active Directory Paths**

Screenshot showing the default database, log file and SYSVOL locations configured for the Domain Controller.

<img width="719" height="366" alt="Screenshot 2026-10-05 135103" src="https://github.com/user-attachments/assets/4bf8bb2a-1987-477d-b65c-5279f3fd15a6" />


## 14. Review Domain Controller Configuration

The Review Options page was used to verify the complete Domain Controller configuration before running the prerequisite checks.

The configuration confirmed that `DOM-DC01` will be configured as the first Active Directory Domain Controller in a new forest.

The selected configuration includes:

| Setting | Value |
|---|---|
| Active Directory Domain | `domconsultancy.local` |
| Forest | `domconsultancy.local` |
| NetBIOS Domain Name | `DOMCONSULTANCY` |
| Forest Functional Level | Windows Server 2025 |
| Domain Functional Level | Windows Server 2025 |
| Global Catalog | Enabled |
| DNS Server | Enabled |
| DNS Delegation | Not configured |

The configuration was reviewed before proceeding to the prerequisite validation stage.

### Evidence

**Evidence 15 — Review AD DS Configuration**

Screenshot showing the final Active Directory Domain Services configuration before prerequisite checks.

<img width="1431" height="729" alt="image" src="https://github.com/user-attachments/assets/a4800c48-d676-4138-9302-97266c7aa49a" />

## 15. Domain Controller Prerequisite Check

The Active Directory Domain Services Configuration Wizard performed a prerequisite check before beginning the Domain Controller promotion.

The validation completed successfully and reported:

**"All prerequisite checks passed successfully."**

A DNS delegation warning was also displayed because an authoritative parent zone for `domconsultancy.local` could not be found.

This warning is expected because `domconsultancy.local` is being created as a new internal Active Directory forest and there is no existing parent DNS infrastructure requiring delegation.

The wizard confirmed that no action was required for the DNS delegation warning.

The server was therefore ready to proceed with the Domain Controller promotion.

### Evidence

**Evidence 16 — Prerequisites Check Passed**

Screenshot showing that all Active Directory Domain Services prerequisite checks passed successfully and that the DNS delegation warning required no action.

<img width="728" height="369" alt="Screenshot 2026-10-05 150525" src="https://github.com/user-attachments/assets/dffd0581-78e8-4531-a416-abfda63766e6" />

## 16. Domain Controller Promotion and Restart

After the Active Directory Domain Services promotion completed, `DOM-DC01` automatically restarted as expected.

Following the restart, the Windows sign-in screen displayed the domain account:

`DOMCONSULTANCY\Administrator`

This confirms that the server has been successfully promoted to a Domain Controller and is now operating within the newly created `domconsultancy.local` Active Directory domain.

The automatic restart was part of the Domain Controller promotion process.

### Evidence

**Evidence 18 — Domain Controller Restart**

Screenshot showing the Windows sign-in screen displaying the `DOMCONSULTANCY\Administrator` domain account after the Domain Controller promotion and restart.

<img width="931" height="487" alt="Screenshot 2026-10-05 151845" src="https://github.com/user-attachments/assets/f3720e55-5811-480c-9431-a1fb9bed4805" />

## 17. Post-Promotion Server Verification

Following the Domain Controller promotion, `DOM-DC01` restarted automatically as part of the installation process.

After logging back into Windows, Server Manager opened successfully and the server was operational.

This confirmed that the server successfully completed the restart associated with the Domain Controller promotion.

Further Active Directory-specific verification was performed using the installed Active Directory management tools.

### Evidence

**Evidence 19 — Post-Promotion Server Manager**

Screenshot showing Server Manager running successfully after the Domain Controller promotion and system restart.

<img width="956" height="485" alt="Screenshot 2026-10-05 153317" src="https://github.com/user-attachments/assets/bdbf84da-e66f-4a3b-a505-6bbc7a6819c0" />



