# Active Directory RBAC Lab 
## Project Overview 
This project demonstrates Role-Based Access Control (RBAC) implementation using Microsoft Active Directory on a 2022 Windows Server. This lab uses Pokémon factions as organizational departments to simulate a real enterprise environment.

## Environment 
- Hypervisor: Oracle VirtualBox
- Server OS: Windows Server 2022
- Domain: izaiahtech.lab
- Domain Controller: WIN-4DVPFHP7GLT

## Faction Structure (RBAC Roles)
| Faction | Role | Access Level |
|---|---|---|
| Team Rocket | IT Admins | Full access, no restrictions |
| Team Aqua | HR Department | No Control Panel or CMD |
| Team Magma | Finance | No USB, hidden C drive |
| Team Galactic | Management | Limited admin access |
| Team Plasma | Security | Audit and compliance only |

### 1. Active Directory Structure
- Domain: izaiahtech.lab
- 5 Organizational Units (OUs)
- 5 Security Groups
- 25 User Accounts (5 per faction)

### 2. Group Policy Objects (GPOs)
Each faction has a dedicated GPO enforcing role-specific restrictions:
- **TeamRocket**: No Restrictions - IT Admin Access
- **TeamAqua**: HR Standard User Policy
- **TeamMagma**: Finance Restricted Access Policy
- **TeamGalactic**: Management Limited Admin Policy
- **TeamPlasma**: Security Audit and Compliance Policy

### 3. Shared Folders with NTFS Permissions
Each faction has a dedicated shared folder with access 
restricted to their group only:
- C:\FactionShares\TeamRocket
- C:\FactionShares\TeamAqua
- C:\FactionShares\TeamMagma
- C:\FactionShares\TeamGalactic
- C:\FactionShares\TeamPlasma

## Screenshots
### OU Structure
![OU Structure](OU%20Structure.jpg)

### Security Groups 



