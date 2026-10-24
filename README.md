# Active Directory Home Lab

A hands-on lab built using Windows Server 2022 in VMware Workstation to simulate a real-world on-premises Active Directory environment. This lab demonstrates core 1st Line IT Support skills including user account management, password resets, and organisational structure setup.

## Lab Environment

| Component | Details |
|-----------|---------|
| Hypervisor | VMware Workstation |
| Server OS | Windows Server 2022 (Desktop Experience) |
| Domain | contoso.local |
| Domain Controller | DC01 |
| Role Installed | Active Directory Domain Services (AD DS) |

## Tasks Completed

### Task 1 - Domain Controller Setup

Installed Windows Server 2022 in a VMware VM and promoted it to a Domain Controller:

- Installed the Active Directory Domain Services (AD DS) role via Server Manager
- Configured a static IP address (192.168.1.10) for reliable DNS operation
- Ran the AD DS Configuration Wizard to promote the server to a Domain Controller
- Created a new forest with root domain: **contoso.local**
- Configured DSRM password for disaster recovery access
- Server restarted and successfully joined as DC01.contoso.local

![AD Overview](01-ad-overview.png)

### Task 2 - Organisational Unit (OU) Structure

Created a logical OU structure to reflect a real company department layout:

- Created three Organisational Units: **IT**, **HR**, and **Finance**
- This mirrors how real organisations structure Active Directory by department
- OUs allow Group Policy to be applied per department and delegate admin control

![OU Structure](02-ou-structure.png)

### Task 3 - User Account Creation and Management

Created user accounts simulating new employee onboarding (Joiner process):

| Name | Username | Department |
|------|----------|------------|
| John Smith | j.smith | IT |
| Sarah Jones | s.jones | HR |
| Mike Taylor | m.taylor | Finance |

Steps taken for each user:
- Created account with first name, last name, and logon name
- Set initial password meeting complexity requirements
- Moved each user into their respective department OU

### Task 4 - Password Reset

Simulated a user calling the helpdesk to report they cannot log in:

- Located the user account in Active Directory Users and Computers
- Right-clicked the account and selected **Reset Password**
- Set a new temporary password
- Ticked **"User must change password at next logon"** for security

![Password Reset](03-reset-password.png)

### Task 5 - Account Disable and Enable

Simulated an employee leaving the organisation (Leaver process):

- Located the user account in Active Directory
- Right-clicked and selected **Disable Account**
- The account icon displayed a downward arrow confirming it was disabled
- Re-enabled the account to demonstrate the reverse process

### Task 6 - Adding User to Security Group

Simulated granting a user elevated access by adding them to a security group:

- Right-clicked John Smith and selected **Add to a group**
- Searched for and added the user to **Domain Admins**
- Used **Check Names** to verify the group name before confirming

![Add to Group](04-add-to-group.png)

## Skills Demonstrated

- Windows Server 2022 installation and configuration
- Active Directory Domain Services (AD DS) installation
- Domain Controller promotion and forest creation
- Static IP configuration for DNS reliability
- Organisational Unit (OU) design and creation
- User account creation, modification, and deletion
- Password resets and account unlocking
- Account disabling for leavers (JML process)
- Security group membership management

## Relevance to IT Support Roles

This lab directly maps to day-to-day 1st Line IT Support responsibilities:

| Real-World Scenario | AD Task Practised |
|--------------------|--------------------|
| New employee starts | Create user account, assign to OU |
| User forgot password | Reset password in AD |
| Account locked after failed logins | Unlock account |
| Employee leaves company | Disable account |
| User needs access to shared drive | Add to security group |
| Department restructure | Move user between OUs |

## Tools Used

- VMware Workstation
- Windows Server 2022 Evaluation
- Active Directory Users and Computers (dsa.msc)
- Server Manager
