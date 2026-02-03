# Active Directory & Help Desk Simulation Lab

## Project Summary
This project simulates a corporate IT environment using **Windows Server 2025**.

Deploying this environment presented a unique challenge. Sourcing a build compatible with my ARM-based MacBook (M-Series) was tricky, as standard server ISOs are incompatible with the architecture. 

Microsoft isn't planning on an ARM compatible public release for Windows Server 2025, but I successfully located an internal build that was originally deployed through the Windows Insider Program. All ARM64 builds for Windows Server '25 were completely wiped without a trace, but a few were (luckily) still available for download via archive.org. 

With the core infrastructure stabilized, the goal was to architect a scalable identity management system from scratch, focusing on **automation**, **security compliance**, and **help desk operations**.

## Key Accomplishments
* **Infrastructure Design:** Architected a Domain Controller with a logical Organizational Unit (OU) structure to mimic a municipal network hierarchy (Police, Finance, HR).
* **Security Enforcement:** Deployed Group Policy Objects (GPOs) to enforce NIST-compliant password complexity (14+ characters) and restrict administrative access.
* **Automation:** Utilized PowerShell scripts to automate user lifecycle events, replacing manual "click-and-create" workflows with efficient bulk provisioning.
* **Access Control:** Implemented Role-Based Access Control (RBAC) to ensure users in sensitive departments have appropriate segregated permissions.

## Technologies Used
* **Host Hardware:** MacBook Pro (Apple Silicon / ARM64)
* **Virtualization:** Parallels Desktop 26
* **OS:** Windows Server 2025 Build 26404 ARM64
* **Identity Management:** Active Directory Domain Services (AD DS)
* **Automation:** PowerShell & ISE

---

## Project Verification

### 1. Organizational Hierarchy (ADUC)
**Structured OU Design:**
Custom Organizational Units were created for departments (Police, Finance, HR) to allow for granular policy application, moving away from the default flat file structure.

![Active Directory Structure](SS%201%20Ad.png)

<br>

### 2. Security Policy Implementation (GPO)
**NIST Compliance:**
Configuration of the "Secure Password Policy" GPO. This setting enforces a minimum password length and complexity requirements to prevent credential-based attacks.

![Group Policy Settings](SS%202%20Password.png)

<br>

### 3. Automation Scripting
**PowerShell User Onboarding:**
This is the script I wrote to automatically onboard users from a .csv. This approach proves the ability to manage users via code rather than GUI alone.

![PowerShell Automation](SS%203%20Script.png)
