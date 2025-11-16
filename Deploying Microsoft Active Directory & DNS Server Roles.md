# Deploying Microsoft Active Directory & DNS Server Roles on Windows Server

## Purpose
This project documents the deployment of a fully functional **Active Directory Domain Services (AD DS)** and **DNS Server** environment on Windows Server. The environment demonstrates centralized identity, authentication, and name resolution services.

Each step in this deployment is explained clearly, and all screenshots are mapped so the process is easy to understand.

---

## Challenge Title
**Deploying Microsoft Active Directory & DNS Server Roles**

---

## Learning Objectives
- Prepare a Windows Server for domain controller functionality  
- Configure a static IP address and hostname  
- Install the AD DS and DNS Server roles  
- Promote the server to a domain controller  
- Configure and verify DNS zones  
- Validate the deployment using management tools and logs  
- Create OUs, users, and security groups in Active Directory  

---

## On-the-Job Scenario
An expanding organization requires centralized account and resource management.  
To support this requirement, a new Windows Server must be configured as:

- A domain controller  
- A DNS server  
- The anchor of a new forest and domain  
- The home for organizational units, users, and groups  

This deployment mirrors a real system administration task in enterprise environments.

---

# Step 1 — Server Setup

## 1.1 Windows Server Installed
Windows Server is already installed and serves as the base OS for domain deployment.

_No screenshot required._

---

## 1.2 Configure a Static IP Address
A domain controller requires a static IP address to remain reachable.

**Screenshots:**  
- static ip address.png  
- hostname, ip static not dhcp.png  

These images show IPv4 settings configured manually, confirming that DHCP is not assigning the server’s IP.

---

## 1.3 Hostname & Server Manager
**Screenshot:**  
- server manager was already installed and look like this.png  

This confirms the hostname and displays Server Manager, the main interface for managing server roles.

---

## 1.4 Network Connectivity Verification
**Screenshots:**  
- verifying connectivity part 1.png  
- verifying connectivity part 2.png  

These images display `ping` tests confirming communication with:

- The local gateway  
- External internet hosts  

---

## 1.5 Windows Server Updates
**Screenshot:**  
- Screenshot 2025-11-07 211408.png  

Displays Windows Update or PowerShell-based update commands.

---

# Step 2 — Install Active Directory and DNS Roles

## 2.1 Open Server Manager
**Screenshot:**  
- open server manager on windows server.png  

Shows navigation to the “Add roles and features” wizard.

---

## 2.2 Add Roles and Features Wizard
**Screenshots:**  
- role basefeature base isntallation.png  
- destinatition server.png  
- server roles.png  
- confirmation.png  

These images show the full process for selecting:

- AD DS  
- DNS Server  
- Required supporting features  

---

# Step 3 — Promotion to Domain Controller

## 3.1 Begin Promotion
**Screenshot:**  
- promote server to domain controller.png  

Shows the post-deployment notification used to start domain controller promotion.

---

## 3.2 Create New Forest & Domain
Domain created:

```
david.local
```

**Screenshot:**  
- forest name.png  

Shows the root domain name entry.

---

## 3.3 Domain Controller Options
**Screenshot:**  
- domain controller options.png  

Displays forest/domain functional levels, DNS server selection, Global Catalog, and DSRM password creation.

---

## 3.4 Prerequisite Check & Review
**Screenshots:**  
- prerequisites check.png  
- review options.png  

Confirm valid configuration and readiness for domain controller promotion.

---

# Step 4 — DNS Configuration

## 4.1 Role Verification
**Screenshot:**  
- verify ad ds dns installation.png  

Shows AD DS and DNS roles installed successfully.

---

## 4.2 Lookup Zone Verification
**Screenshot:**  
- confirm forward and reverse lookup zones are functioning.png  

Shows the Forward Lookup Zone, reverse lookup zone container, and `_msdcs` domain records.

---

# Step 5 — Validation

## 5.1 ADUC (Active Directory Users and Computers)
**Screenshot:**  
- active directory users and computers and dns.png  

Confirms the domain structure loaded correctly.

---

## 5.2 DNS Resolution Tests
**Screenshot:**  
- test dns resolution.png  

Shows `nslookup` and `ping` resolving the domain name and reaching the domain controller IP.

---

## 5.3 Event Viewer Logs
**Screenshots:**  
- event logs.png  
- event logs better.png  

Displays system and directory service logs confirming no critical errors.

---

# Step 6 — Organizational Units, Users, and Groups

## 6.1 Create an Organizational Unit
OU created:

```
David_Admins
```

**Screenshot:**  
- organizational units.png  

---

## 6.2 Create a User
**Screenshots:**  
- created a user inside david_admins organizational unit.png  
- put password A@123456789.png  
- added password A@1234.png  

Show a user account created within the OU.

---

## 6.3 Create a Security Group
Group name:

```
David_Groups
```

**Screenshot:**  
- created group.png  

---

## 6.4 Final Verification
**Screenshot:**  
- proof to show the user and the group was created and on the bottom left you can see the organizational unit called david_admins.png  

Shows all objects created successfully.

---

# Deployment Summary
This project completes a full Active Directory and DNS setup, demonstrating:

- Server preparation  
- Static IP assignment  
- AD DS role installation  
- DNS role configuration  
- Domain controller promotion  
- DNS zone validation  
- Domain verification  
- OU, user, and group creation  

It represents a working example of an enterprise Windows Server domain.

