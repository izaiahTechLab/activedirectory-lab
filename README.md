# Active Directory RBAC Lab 🎮

## Overview
This project demonstrates Role-Based Access Control (RBAC) 
Implementation using Microsoft Active Directory on a 2022 Windows 
Server. The Pokémon factions are used as organizational 
departments to simulate a real enterprise environment.

## Environment
| Component | Details |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Domain | izaiahtech.lab |
| Domain Controller | WIN-4DVPFHP7GLT |

## RBAC Faction Structure
| Faction | Role | Access Level |
|---|---|---|
| Team Rocket | IT Admins | Full access |
| Team Aqua | HR | Limited access |
| Team Magma | Finance | Restricted access |
| Team Galactic | Management | Moderate access |
| Team Plasma | Security | Audit and compliance |

## What Was Built
- Active Directory domain on Windows Server 2022
- 5 Organizational Units with 25 users
- Role-based security groups per faction
- Group Policy Objects enforcing access restrictions
- Shared folders with NTFS permissions per faction

## Project Walkthrough
For a full step-by-step breakdown, see the
[Project Walkthrough](walkthrough/WALKTHROUGH.md)

## Skills Demonstrated
- Active Directory administration
- Group Policy management
- RBAC implementation
- PowerShell automation
- NTFS permissions
- Network security principles
