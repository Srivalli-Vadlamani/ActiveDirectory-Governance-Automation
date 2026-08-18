#  Enterprise Active Directory Governance & RBAC Staging Suite

A PowerShell automation and administration tool engineered to enforce Role-Based Access Control (RBAC), streamline bulk user lifecycle management, and perform Active Directory security hygiene audits.

##  Key Features

* RBAC Bulk Provisioning: Ingests structured CSV employee data to dynamically assign Organizational Units (OUs), configure User Principal Names (UPNs), apply Department security groups, and enforce first-logon password change requirements.
* OU Hierarchy & Group Staging: Validates target container structures to ensure strict identity governance and clean domain architecture.
* Inactive Account Detection: Audits stale computer/user objects inactive for 90+ days to mitigate lateral attack surfaces.
* Password Policy Auditing: Identifies accounts configured with non-compliant `PasswordNeverExpires` attributes.
* Orphaned Group Hygiene: Detects empty domain security groups to minimize administrative bloat.

##  Technology Stack

* Scripting: PowerShell 5.1 / PowerShell 7+
* Module Dependencies: `ActiveDirectory` Module / Remote Server Administration Tools (RSAT)
* Identity Infrastructure: Microsoft Active Directory Domain Services (AD DS), Group Policy Objects (GPOs), RBAC

##  Repository Structure

| File | Purpose |
| :--- | :--- |
| `Invoke-ADGovernanceSuite.ps1` | Core automation script for RBAC provisioning and security audits |
| `NewUsers_Template.csv` | Sample schema for automated user staging |
| `README.md` | Architecture and implementation documentation |


##  Usage

### Run Provisioning and Audit:
```powershell
.\Invoke-ADGovernanceSuite.ps1 -CsvPath ".\NewUsers_Template.csv" -InactiveDays 90
