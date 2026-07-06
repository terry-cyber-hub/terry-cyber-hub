# Active Directory Domain Services (AD DS) Infrastructure Lab

## Project Overview
This project demonstrates the deployment, configuration, and management of an enterprise Active Directory environment from scratch using Windows Server 2022. The objective was to move beyond theoretical identity management and build a functional, secure domain infrastructure. This involved promoting a standalone server to a Domain Controller (DC), establishing a logical Organizational Unit (OU) hierarchy, managing user objects and security groups, and validating authentication workflows.

## Infrastructure & Architecture
The entire environment was deployed as a real cloud infrastructure instance, ensuring a production-like setup:

* **Operating System:** Windows Server 2022 Datacenter
* **Deployment Platform:** Microsoft Azure Virtual Machines
* **Server Role:** Domain Controller (Root of the forest)
* **Domain Name:** `cyberlab.local`
* **NetBIOS Name:** `CYBERLAB`

---

## Deployment Steps

### 1. VM Provisioning & Networking
* Deployed a Windows Server 2022 virtual machine in Azure to act as the core infrastructure host.
* Configured static IP mapping internal to the virtual network to ensure the server maintains a permanent identity for identity and DNS services.

### 2. Active Directory Domain Services Installation
* Utilized Server Manager to install the **Active Directory Domain Services (AD DS)** role along with the required management tools.
* Formally promoted the server to a **Domain Controller**, initiating a brand-new forest named `cyberlab.local`.
* Configured and verified the integrated **DNS Server** role, which handles the essential SRV resource records required for domain locators.

### 3. Structural Design (OU Hierarchy)
To mirror a structured corporate environment and prepare for future Group Policy Objects (GPOs), a clean Organizational Unit hierarchy was built in Active Directory Users and Computers (ADUC):
* Created a primary top-level OU for the organization.
* Formed nested sub-OUs separating corporate assets: `Departments`, `Staff`, `Groups`, and `Computers`.

### 4. Identity Management & Security Groups
* **User Provisioning:** Created standard user accounts within the target OUs using both the graphical interface (ADUC) and automated administration via PowerShell. Configured accounts for core staff members:
  * `Noble Hirwa`
  * `Leo Messi`
  * `Terry Shema`
* **Access Control:** Built explicit **Security Groups** (e.g., Global Security Groups) to manage permissions cleanly. Assigned users to their respective groups to practice the industry-standard principle of managing access via group memberships rather than individual user accounts.

---

## Validation & Verification

Success and stability of the Active Directory deployment were validated directly through system checks and administrative consoles:

1.  **Domain Controller Health:** Verified successful promotion by checking the presence of the `SYSVOL` and `NETLOGON` shared folders, confirming the active replication state.
2.  **DNS Resolution:** Validated proper DNS functionality using network diagnostics (`nslookup`), ensuring the domain name `cyberlab.local` correctly resolves to the Domain Controller's private IP.
3.  **Active Directory Database Integrity:** Confirmed that all built OUs, security groups, and user accounts successfully populated the NTDS database and were completely searchable.
4.  **Authentication Testing:** Successfully tested domain authentication and token generation by executing mock logins for the newly created accounts, validating that group memberships mapped perfectly to user security tokens.

---

## Key Takeaways
* **Logical Segmentation:** Designing a clean OU structure from day one is critical for delegating administrative privileges and targeting Group Policy Objects effectively.
* **Scalability via Automation:** Utilizing PowerShell for user creation highlights the importance of automation in systems administration when scaling from a few users to hundreds.
* **Centralized Identity:** This lab underscores how Active Directory serves as the single source of truth for identity, authentication, and security auditing across an entire enterprise network.
* ** Screenshots:
* <img width="455" height="212" alt="Screenshot 2026-05-20 200442" src="https://github.com/user-attachments/assets/0f7a5a5a-4b45-4432-813d-cfa56af399cf" />
<img width="467" height="272" alt="Screenshot 2026-05-20 200854" src="https://github.com/user-attachments/assets/51ebfa9c-c682-4e8f-b3f6-287d659242a8" />


