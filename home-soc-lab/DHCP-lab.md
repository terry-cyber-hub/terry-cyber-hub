# Windows Server DHCP Configuration Lab

## Project Overview
This project demonstrates the deployment, configuration, and validation of a multi-scope DHCP environment using Windows Server 2022 within an isolated laboratory environment. The objective was to transition from theoretical networking concepts (such as the DORA process) to a real-world enterprise deployment, ensuring proper network segmentation, IP address management (IPAM), and resource reservation.

## Network Architecture & Scopes
The DHCP server (`dc1`) was configured with three distinct scopes to support an enterprise network hierarchy:

| Scope Name | Subnet / Purpose | Key Options Configured |
| :--- | :--- | :--- |
| **Users LAN** | General corporate staff devices | Router (Gateway), DNS Server, Domain Name |
| **Corporate Voice** | Dedicated VoIP infrastructure | Router (Gateway), DNS Server, Domain Name |
| **Guest Wi-Fi** | Isolated guest network | Router (Gateway), DNS Server, Domain Name |

### Scope Options Applied
To ensure clients receive proper network configuration automatically, the following DHCP options were defined globally or per scope:
* **003 Router:** Configured to the specific subnet gateway (e.g., ending in `.254`).
* **006 DNS Servers:** Pointed directly to the Active Directory Domain Controller (`dc1`).
* **015 DNS Domain Name:** Set to the local lab domain (`lab.local`).

---

## Deployment Steps

### 1. Role Installation
* Installed the **DHCP Server Role** via Server Manager on `dc1`.
* Completed the post-deployment configuration wizard to create the local `DHCP Administrators` and `DHCP Users` security groups.

### 2. Scope Creation & IPAM
* Defined the IP address pools and subnet masks for all three target networks.
* **Exclusions:** Configured IP address exclusions at the beginning of the pools (e.g., reserving `.1` through `.20` for static infrastructure like switches, gateways, and servers) to prevent IP conflicts.

### 3. Active Directory Authorization
* Authorized the DHCP server within Active Directory to prevent rogue DHCP servers from disrupting network traffic.

### 4. DHCP Reservation
* Created a permanent IP reservation within the **Users LAN** scope for a network printer (`Printer-01`):
    * **Reserved IP:** `192.168.1.15`
    * **MAC Address Mapping:** `00-11-22-33-44-55`

---

## Validation & Verification

Because this lab runs in an isolated infrastructure environment without live client machines, success was validated directly via the **DHCP Management Console**:

1.  **Service Status:** Confirmed the root server node (`dc1`) displays a **green checkmark**, indicating the service is fully authorized and actively running.
2.  **Scope Activation:** Verified that all three scopes are live. In the console tree, the scope folders display normal active icons without any red down-arrows (which signify a deactivated state).
3.  **Database Inspection:** * Navigated to `Address Pool` to confirm exclusion ranges are properly flagged with the red exclusion icon.
    * Navigated to `Reservations` to verify that `Printer-01` is actively bound to its explicit MAC address in the server database.

---

## Key Takeaways
* **Preventing Conflicts:** Implementing strict exclusion ranges ensures crucial infrastructure maintains static IPs without risk of the DHCP server leasing those addresses to standard clients.
* **Automation via Options:** Utilizing DHCP options eliminates the need to manually configure client DNS settings or default gateways, reducing human error in network scaling.
* **Security Context:** Understanding the requirement for Active Directory authorization highlights how enterprise environments defend against unauthorized network services.
* ** Screenshot: <img width="515" height="391" alt="image" src="https://github.com/user-attachments/assets/c111f85c-5817-48e0-ba76-e372b4378dcf" />
