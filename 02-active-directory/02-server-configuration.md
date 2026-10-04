## 1. Server Naming

The Windows Server initially used an automatically generated hostname:

`WIN-RDTGML56CMQ`

The server was renamed to:

`DOM-DC01`

The naming convention identifies:

- `DOM` — DomConsultancy
- `DC` — Domain Controller
- `01` — First Domain Controller in the lab

The server remains a member of `WORKGROUP` at this stage because Active Directory Domain Services has not yet been installed.

### Evidence

**Evidence 01 — Current Server Identity**

The initial automatically generated server hostname was identified before configuration.

<img width="953" height="503" alt="Screenshot 2026-10-04 185638" src="https://github.com/user-attachments/assets/d0fe714b-3aa6-4bc8-baa5-922fc2e4c38f" />


**Evidence 02 — Server Renamed to DOM-DC01**

<img width="630" height="455" alt="Screenshot 2026-10-04 191809" src="https://github.com/user-attachments/assets/61b226d8-495d-47c0-918a-5c522ea22d3f" />


The server was successfully renamed to `DOM-DC01`.


## 2. Initial Network Configuration

The server was initially configured to obtain its IPv4 network configuration automatically through DHCP.

The Ethernet adapter was verified to have active IPv4 connectivity before changing the configuration.

### Evidence

**Evidence 03 — Network Adapter**

Screenshot showing the Ethernet network adapter configured for the lab server.

<img width="737" height="380" alt="Screenshot 2026-10-04 192300" src="https://github.com/user-attachments/assets/6218a78d-a1b0-4c3b-bdc3-1437988e0b01" />


**Evidence 04 — Ethernet Status**

Screenshot confirming active IPv4 connectivity and the current DHCP-based network connection.

<img width="631" height="368" alt="Screenshot 2026-10-04 192446" src="https://github.com/user-attachments/assets/f8ced416-bee2-47b4-b8bc-8e0ef100f33d" />



