# Enterprise Windows Server Infrastructure

## 📖 Project Overview
[cite_start]This project demonstrates the design and implementation of a complex **Windows Server 2019/2022** infrastructure for the **Information Technology Institute (ITI)**[cite: 15]. [cite_start]It utilizes a multi-domain forest architecture to simulate real-world enterprise networking and centralized management scenarios[cite: 16].



[cite_start]The environment integrates core identity services, automation, and security hardening to provide a realistic testing ground for enterprise-level administration[cite: 17, 22].

---

## 🛠️ Key Implementations

### 1. Active Directory Hierarchy & High Availability
* [cite_start]**Forest Structure:** Established a root domain (`ITI.Local`) with two regional child domains (`Alex.ITI.Local` and `Ism.ITI.Local`) to represent organizational branches[cite: 19, 162].
* [cite_start]**Redundancy:** Deployed an **Additional Domain Controller (ADC)** to establish high availability, load balancing, and eliminate single points of failure[cite: 106, 109].
* [cite_start]**Secure Branch Operations:** Implemented a **Read-Only Domain Controller (RODC)** for remote sites, featuring specific Password Replication Policies (PRP) to protect sensitive credentials in higher-risk locations[cite: 216, 220, 222].

### 2. Operational Automation
* [cite_start]**Mass User Creation:** Leveraged **PowerShell scripting** to automatically generate 50 domain users with standardized naming conventions and security settings[cite: 490, 496, 501].
* [cite_start]**Windows Deployment Services (WDS):** Configured a PXE-boot environment to automate the mass deployment of Windows 10 OS images to client machines[cite: 607, 608, 868].

### 3. Centralized Policy Management (GPO)
* [cite_start]**Security Hardening:** Enforced restrictions on specific users, including blocking access to the Control Panel and disabling USB/removable storage[cite: 878, 911].
* [cite_start]**Software Deployment:** Automated the installation of **WinRAR.msi** across target workstations via GPO[cite: 1079, 1082].
* [cite_start]**Desktop Environment:** Standardized the corporate identity by enforcing the ITI logo wallpaper across the domain[cite: 924, 957].

### 4. Network & Web Services
* [cite_start]**DNS/DHCP Integration:** Configured primary and secondary DNS servers for fault-tolerant name resolution, alongside a dedicated DHCP scope for automated client IP assignment[cite: 379, 407, 438, 440].
* [cite_start]**IIS & FTP Management:** Hosted multiple web portals using host headers on a single IP and managed web asset backups via an authenticated FTP lifecycle[cite: 358, 1426, 1428].

---

## 🔒 Security & Delegation
[cite_start]The project strictly adheres to the **Principle of Least Privilege (PoLP)**[cite: 21]:
* [cite_start]**Administrative Delegation:** Granted specific users (e.g., User B) the ability to manage servers via RDP without adding them to high-privilege groups like Domain Admins[cite: 1150].
* [cite_start]**RODC Management:** Delegated local server maintenance tasks to non-admin helpdesk accounts[cite: 217, 218].
