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

## 5. Static IPv4 Configuration

The server was configured with a static IPv4 address to provide a predictable network identity for the future Domain Controller.

The DHCP-assigned address `10.0.2.15` was replaced with the static address `10.0.2.10`.

The following configuration was applied:

| Setting | Value |
|---|---|
| IPv4 Address | 10.0.2.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.0.2.2 |
| Preferred DNS Server | 10.0.2.2 |
| Alternate DNS Server | Not configured |

A static IP address is important for a Domain Controller because other systems and services need to consistently locate the server.

### Evidence

**Evidence 07 — Current DHCP Configuration**

Screenshot showing that IPv4 was initially configured to obtain the IP address and DNS server automatically.

<img width="433" height="355" alt="Screenshot 2026-10-04 193448" src="https://github.com/user-attachments/assets/ccb5372b-3d20-480d-a8bc-e35055ad226b" />


**Evidence 08 — Static IP Configuration**

Screenshot showing the static IPv4 configuration before it was applied to `DOM-DC01`.

<img width="435" height="305" alt="Screenshot 2026-10-04 194410" src="https://github.com/user-attachments/assets/5221b34d-825f-4416-aa61-249e61aa2d58" />


---

## 6. Network Configuration Verification

After applying the static IPv4 configuration, the network connection details were reviewed to verify that the static IP address had been successfully applied.

The server was configured with the following static IPv4 settings:

| Setting | Value |
|---|---|
| DHCP Enabled | No |
| IPv4 Address | 10.0.2.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.0.2.2 |

At this stage, the DNS server was temporarily configured as `10.0.2.2`. Although the static IP configuration was successfully applied, subsequent DNS testing showed that `10.0.2.2` was not successfully resolving external DNS queries.

The static IP configuration itself was confirmed to be working correctly, and the DNS issue was investigated separately in the following troubleshooting section.

### Evidence

**Evidence 09 — Static IP Verification**

Screenshot showing that DHCP was disabled and that `DOM-DC01` was using the static IPv4 address `10.0.2.10`.

<img width="361" height="299" alt="Screenshot 2026-10-04 194958" src="https://github.com/user-attachments/assets/7e5cbdda-3505-4c3a-8a8a-90de15b75514" />


## 7. DNS Troubleshooting

The initial static IPv4 configuration used the VirtualBox NAT gateway (`10.0.2.2`) as the DNS server.

Although `DOM-DC01` had network connectivity, external DNS name resolution was not working correctly. DNS troubleshooting was performed to identify and resolve the issue.

### 7.1 Test Connectivity to the Default Gateway

The first step was to verify that `DOM-DC01` could communicate with the configured default gateway.

The following command was used:

```text
ping 10.0.2.2
```

The gateway responded successfully, confirming that `DOM-DC01` could communicate with the VirtualBox NAT gateway.

This established that the server's local network configuration and connection to the VirtualBox NAT network were functioning correctly.

### Evidence

**Evidence 10 — Default Gateway Connectivity Test**

`Evidence-10-Gateway-Connectivity-Test.png`

Screenshot showing the successful `ping 10.0.2.2` test and confirming connectivity between `DOM-DC01` and the VirtualBox NAT gateway.

<img width="496" height="298" alt="Screenshot 2026-10-04 195627" src="https://github.com/user-attachments/assets/03d93dc8-c7e3-4485-9a67-5ba348e6a21f" />


---

### 7.2 Test External Network Connectivity

After confirming connectivity to the default gateway, external IP connectivity was tested.

The following command was used:

```text
ping 8.8.8.8
```

The server received responses from the external IP address.

This confirmed that `DOM-DC01` had external network connectivity and that the issue was unlikely to be caused by the static IP address, subnet mask, or default gateway.

### Evidence

**Evidence 10 — External Connectivity Test**

`Evidence-10-External-Connectivity-Test.png`

Screenshot showing the `ping 8.8.8.8` test and confirming external IP connectivity.

<img width="522" height="162" alt="Screenshot 2026-10-04 200413" src="https://github.com/user-attachments/assets/dc72830b-dc1f-4c6a-af9c-9bbd59eb6e14" />


---

### 7.3 Test DNS Resolution

After confirming network connectivity, DNS name resolution was tested.

The following command was used:

```text
nslookup google.com
```

The DNS lookup failed while the VirtualBox NAT gateway (`10.0.2.2`) was configured as the DNS server.

The request timed out and returned a `Server Unknown` response.

This demonstrated that the server had network connectivity but was unable to resolve external domain names using the configured DNS server.

The troubleshooting process therefore identified DNS resolution as the issue rather than general network connectivity.

### Evidence

**Evidence 11 — DNS Resolution Failure**

`Evidence-11-DNS-Resolution-Failure.png`

Screenshot showing the failed `nslookup google.com` test, including the timeout and `Server Unknown` response from `10.0.2.2`.

<img width="442" height="203" alt="Screenshot 2026-10-04 200604" src="https://github.com/user-attachments/assets/89cee33e-bf6e-448d-8083-94650bfa7de7" />


---

### 7.4 Correct the DNS Configuration

The original DHCP network configuration was reviewed to identify the DNS servers that had been provided automatically before the server was assigned a static IP address.

The DHCP configuration had provided the following DNS servers:

| Setting | Value |
|---|---|
| Preferred DNS | `194.168.4.100` |
| Alternate DNS | `194.168.8.100` |

The DNS configuration on `DOM-DC01` was updated using these DNS servers while retaining the static IPv4 address.

The corrected network configuration was:

| Setting | Value |
|---|---|
| IPv4 Address | `10.0.2.10` |
| Subnet Mask | `255.255.255.0` |
| Default Gateway | `10.0.2.2` |
| Preferred DNS | `194.168.4.100` |
| Alternate DNS | `194.168.8.100` |

The static IP address and default gateway were not changed. Only the DNS configuration was corrected.

### Evidence

**Evidence 12 — DNS Configuration Correction**

`Evidence-12-DNS-Configuration-Correction.png`

Screenshot showing the corrected IPv4 configuration with:

- Static IP: `10.0.2.10`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `10.0.2.2`
- Preferred DNS: `194.168.4.100`
- Alternate DNS: `194.168.8.100`

<img width="385" height="291" alt="Screenshot 2026-10-04 200921" src="https://github.com/user-attachments/assets/c6303fa7-9d29-43e7-b65d-62b03ed3ae45" />

---

### 7.5 Verify DNS Resolution

After applying the corrected DNS configuration, the DNS lookup was performed again.

The following command was used:

```text
nslookup google.com
```

The lookup successfully resolved `google.com` and returned multiple IPv4 and IPv6 addresses.

The successful response confirmed that external DNS name resolution had been restored.

This verified that the DNS configuration correction resolved the issue without changing the server's static IP address or default gateway.

### Evidence

**Evidence 13 — DNS Resolution Success**

`Evidence-13-DNS-Resolution-Success.png`

Screenshot showing the successful `nslookup google.com` result and confirming that `194.168.4.100` was successfully resolving external DNS queries.

<img width="448" height="214" alt="Screenshot 2026-10-04 201248" src="https://github.com/user-attachments/assets/fa3a813f-7251-4622-9f47-49b2218858ba" />


---

### 7.6 Troubleshooting Outcome

The DNS troubleshooting process demonstrated the following:

1. The server could communicate with the VirtualBox NAT gateway.
2. The server had external IP connectivity.
3. The static IPv4 configuration was functioning correctly.
4. DNS resolution failed when `10.0.2.2` was configured as the DNS server.
5. The original DHCP DNS configuration was reviewed.
6. The DNS configuration was changed to `194.168.4.100` and `194.168.8.100`.
7. DNS resolution was successfully restored.
8. The server retained the static IPv4 address `10.0.2.10`.

This troubleshooting exercise demonstrated the ability to distinguish between **network connectivity problems and DNS resolution problems**, which is an important troubleshooting skill when preparing a Windows Server environment for Active Directory.

### Evidence Summary

| Evidence | Screenshot | Purpose |
|---|---|---|
| Evidence 10 | `Evidence-10-External-Connectivity-Test.png` | Confirms external IP connectivity |
| Evidence 11 | `Evidence-11-DNS-Resolution-Failure.png` | Shows the initial DNS resolution failure |
| Evidence 12 | `Evidence-12-DNS-Configuration-Correction.png` | Shows the corrected DNS configuration |
| Evidence 13 | `Evidence-13-DNS-Resolution-Success.png` | Confirms successful DNS resolution |

### Active Directory DNS Consideration

The external DNS configuration used during the initial Windows Server setup is temporary.

Once Active Directory Domain Services and the DNS Server role are installed, `DOM-DC01` will provide internal DNS services for the Active Directory domain.

External DNS resolution will subsequently be handled through DNS forwarders configured on the internal DNS server.

## 8. Windows Update and Security Patch Verification

Before proceeding with the Active Directory configuration, Windows Update was checked to ensure that the Windows Server environment had the latest available security updates.

The initial Windows Update check identified several pending updates, including:

- Microsoft Defender Antivirus security intelligence update
- Windows security update
- .NET Framework security update
- Windows Security platform update
- Windows Malicious Software Removal Tool

The available updates were installed and the server was restarted where required.

Windows Update was then checked again to verify the final update status.

The server reported:

**"You're up to date"**

This confirmed that the available Windows updates had been successfully installed.

### Evidence

**Evidence 14 — Windows Updates Pending**

Screenshot showing the security and system updates identified before remediation.

<img width="584" height="383" alt="Screenshot 2026-10-04 203553" src="https://github.com/user-attachments/assets/799c09d6-ff1a-4a93-8898-ceeaec729dea" />


**Evidence 15 — Windows Updates Completed**

Screenshot showing Windows Update reporting that `DOM-DC01` is up to date.

<img width="758" height="405" alt="Screenshot 2026-10-05 085033" src="https://github.com/user-attachments/assets/dba94dba-3503-4797-acde-075058e79855" />



### Security Consideration

Applying current security updates before installing Active Directory helps ensure that the server starts the domain controller deployment from a properly patched baseline.

Keeping the operating system and security components updated is also an important security control for infrastructure servers.
