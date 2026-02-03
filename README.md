# Enterprise Windows Server Infrastructure

## 📖 Project Overview
This project demonstrates the design and implementation of a complex Windows Server infrastructure for the Information Technology Institute (ITI). It utilizes a multi-domain forest architecture to simulate real-world enterprise networking scenarios. The environment integrates core services including Active Directory, DNS, DHCP, IIS, and Windows Deployment Services (WDS) to provide centralized management, security, and automation.

---

## 🛠️ Key Implementations

### 1. Active Directory Hierarchy & High Availability
* **Forest Structure:** Established a root domain (`ITI.Local`) with regional child domains (`Alex.ITI.Local` and `Ism.ITI.Local`) to represent organizational branches.
* **Redundancy:** Deployed an **Additional Domain Controller (ADC)** to establish high availability and eliminate single points of failure.
* **Primary Authority:** The **Primary Domain Controller (DC1)** serves as the central authority for trust management, policy synchronization, and global catalog services.
* **Secure Branch Operations:** Implemented a **Read-Only Domain Controller (RODC)** for remote sites with specific Password Replication Policies to protect administrative credentials.

### 2. Operational Automation
* **Mass User Creation:** Developed a **PowerShell script** to automatically generate 50 domain users (pc01 to pc50), ensuring naming consistency and reducing manual configuration errors.
* **Windows Deployment Services (WDS):** Configured a centralized system for mass OS deployment, enabling the automated installation of Windows 10 on new computers via PXE boot.

### 3. Centralized Policy Management (GPO)
* **Security Hardening:** Enforced strict user restrictions, including blocking access to the Control Panel and denying access to removable storage/flash memory.
* **Software Deployment:** Automated the installation of **WinRAR** as an assigned package to ensure it installs automatically during system boot.
* **User Mobility:** Configured **Roaming Profiles** to ensure that user data (Desktop, Documents, etc.) is saved to a central server and accessible from any authorized workstation.

### 4. Network & Web Services
* **Infrastructure Services:** Integrated **DNS** for fault-tolerant name resolution and a **DHCP** scope for automated client IP assignment.
* **Web Hosting:** Deployed **Internet Information Services (IIS)** to host multiple web portals (www.web1.com and www.web2.com) using host headers on a single IP address

---

## 📁 Project Documentation
📄 **[View Full Project PDF](./final.pdf)**
