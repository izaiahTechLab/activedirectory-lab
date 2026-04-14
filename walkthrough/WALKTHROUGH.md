# Project Walkthrough

## Table of Contents
1. [Environment Setup](#1-environment-setup)
2. [Domain Controller Setup](#2-domain-controller-setup)
3. [Organizational Unit Structure](#3-organizational-unit-structure)
4. [Security Groups](#4-security-groups)
5. [User Accounts](#5-user-accounts)
6. [Group Policy Objects](#6-group-policy-objects)
7. [Shared Folders and NTFS Permissions](#7-shared-folders-and-ntfs-permissions)

---

## 1. Environment Setup
VirtualBox was used to create a virtual machine running 
Windows Server 2022. The VM was configured with the 
following specifications:

| Setting | Value |
|---|---|
| RAM | 4GB |
| CPU | 2 Cores |
| Storage | 50GB |
| Network | NAT Network |
| OS | Windows Server 2022 |

---

## 2. Domain Controller Setup
After installing Windows Server 2022, the server was promoted
to a Domain Controller using the AD DS role.

- Domain Name: izaiahtech.lab
- Domain Controller Name: WIN-4DVPFHP7GLT
- Forest Functional Level: Windows Server 2022

---

## 3. Organizational Unit Structure
Six OUs were created under the Pokémon parent OU to organize
users and groups by faction role.

![OU Structure](../screenshots/OU_Structure.jpg)

---

## 4. Security Groups
A security group was created for each faction inside the 
Groups OU. Users are assigned to their faction group to 
inherit the correct access permissions.

---

## 5. User Accounts
25 users were created across 5 faction OUs using PowerShell.
Each user was automatically assigned to their faction 
security group.

### Team Aqua (HR)
![TeamAqua Users](../screenshots/Team_Aqua_Users.jpg)

### Team Rocket (IT Admins)
![TeamRocket Users](../screenshots/Team_Rocket_Users.jpg)

### Team Magma (Finance)
![TeamMagma Users](../screenshots/Team_Magma_Users.jpg)

### Team Galactic (Management)
![TeamGalactic Users](../screenshots/Team_Galactic_Users.jpg)

### Team Plasma (Security)
![TeamPlasma Users](../screenshots/Team_Plasma_Users.jpg)

---

## 6. Group Policy Objects
A GPO was created and linked to each faction's OU to enforce
role-based access restrictions.

| Faction | GPO Name | Key Restrictions |
|---|---|---|
| TeamRocket | No Restrictions - IT Admin Access | Full access |
| TeamAqua | HR Standard User Policy | No Control Panel, No CMD |
| TeamMagma | Finance Restricted Access Policy | No USB, Hidden C Drive |
| TeamGalactic | Management Limited Admin Policy | No Control Panel, No CMD |
| TeamPlasma | Security Audit and Compliance Policy | Audit logging enabled |

---

## 7. Shared Folders and NTFS Permissions
Shared folders were created for each faction with NTFS
permissions restricting access to the owning group only.

| Folder Path | Authorized Group |
|---|---|
| C:\FactionShares\TeamRocket | TeamRocket |
| C:\FactionShares\TeamAqua | TeamAqua |
| C:\FactionShares\TeamMagma | TeamMagma |
| C:\FactionShares\TeamGalactic | TeamGalactic |
| C:\FactionShares\TeamPlasma | TeamPlasma |
