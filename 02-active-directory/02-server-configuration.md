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

## 3. Initial Network Details

The server was initially configured to obtain its IPv4 configuration through DHCP.

The following network information was identified before configuring a static address:

| Setting | Value |
|---|---|
| IPv4 Address | 10.0.2.15 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.0.2.2 |
| DHCP | Enabled |
| DHCP Server | 10.0.2.2 |
| DNS Servers | 194.168.4.100 / 194.168.8.100 |

The server was successfully communicating through the VirtualBox NAT network.

### Evidence

**Evidence 05 — Current Network Details**

Screenshot showing the DHCP-assigned IPv4 address, subnet mask, gateway and DNS configuration.

<img width="359" height="308" alt="Screenshot 2026-10-04 192823" src="https://github.com/user-attachments/assets/8c221b76-e05d-409e-aef3-c0a97c069eeb" />


## 4. IPv4 Network Configuration

The Ethernet adapter properties were reviewed to prepare the server for static IPv4 configuration.

Internet Protocol Version 4 (TCP/IPv4) was selected because the Domain Controller will require a predictable network address.

### Evidence

**Evidence 06 — Ethernet Properties**

Screenshot showing the Ethernet adapter properties and available IPv4 networking component.

<img width="739" height="627" alt="image" src="https://github.com/user-attachments/assets/5db4d059-8714-4b25-95f5-e3c2a1baf697" />





