# 🖥️ Deploying Microsoft Active Directory & DNS Server Roles on Windows Server

## 📌 Purpose
This project demonstrates how a Windows Server environment can be configured to operate as a fully functional **Active Directory Domain Controller** with an integrated **DNS Server**. Active Directory enables centralized management of users, computers, permissions, and authentication. DNS enables reliable name resolution throughout the environment.

This deployment follows real-world processes used by IT departments to build and maintain domain infrastructures.

## 🏷️ Challenge Title
**Deploying Microsoft Active Directory & DNS Server Roles**

## 🎓 Learning Objectives
- Understand prerequisites for deploying Active Directory and DNS  
- Install and configure Active Directory Domain Services (AD DS)  
- Install and configure DNS Server role  
- Promote a Windows Server to a domain controller  
- Validate domain and DNS functionality  
- Create Organizational Units (OUs), user accounts, and security groups  

## 📘 On-the-Job Scenario
An expanding organization requires a centralized identity and resource management system.  
A Windows Server will be configured to support:

- A new Active Directory forest  
- A new domain  
- DNS services  
- Organizational Units  
- Domain users  
- Security groups  

This deployment replicates a common project assigned to junior system administrators supporting enterprise networks.

---

# 🧩 Challenge Steps

Below are the full deployment steps, including where to place supporting screenshots.

---

# 🔵 Step 1 — Server Setup

## 1.1 Windows Server Installed
Windows Server installation completed successfully.  
_No screenshot required._

## 1.2 Configure a Static IP Address
A static IP address ensures the server remains reachable with a permanent network location.

📁 Place screenshots into:  
`screenshots/1_server_setup/`
- static ip address.png  
- hostname, ip static not dhcp.png  

## 1.3 Hostname and Server Manager
📁 Place into:  
`screenshots/1_server_setup/`
- server manager was already installed and look like this.png  

## 1.4 Network Connectivity Verification
📁 Place into:  
`screenshots/1_server_setup/`
- verifying connectivity part 1.png  
- verifying connectivity part 2.png  

## 1.5 Windows Server Updates
📁 Place into:  
`screenshots/1_server_setup/`
- Screenshot 2025-11-07 211408.png  

---

# 🟣 Step 2 — Install Active Directory and DNS Roles

## 2.1 Access Server Manager
📁 Place into:  
`screenshots/2_ad_ds_dns_installation/`
- open server manager on windows server.png  

## 2.2 Add Roles and Features
📁 Place into:  
`screenshots/2_ad_ds_dns_installation/`
- role basefeature base isntallation.png  
- destinatition server.png  
- server roles.png  
- confirmation.png  

---

# 🟢 Step 3 — Promotion to Domain Controller

## 3.1 Promote to Domain Controller
📁 Place into:  
`screenshots/3_dc_promotion/`
- promote server to domain controller.png  

## 3.2 Create a New Forest and Domain
Domain created: `david.local`

📁 Place into:  
`screenshots/3_dc_promotion/`
- forest name.png  

## 3.3 Domain Controller Options
📁 Place into:  
`screenshots/3_dc_promotion/`
- domain controller options.png  

## 3.4 Prerequisite Check and Review
📁 Place into:  
`screenshots/3_dc_promotion/`
- prerequisites check.png  
- review options.png  

---

# 🟡 Step 4 — DNS Configuration

## 4.1 DNS Role Verification
📁 Place into:  
`screenshots/4_dns_configuration/`
- verify ad ds dns installation.png  

## 4.2 Lookup Zone Verification
📁 Place into:  
`screenshots/4_dns_configuration/`
- confirm forward and reverse lookup zones are functioning.png  

---

# 🔴 Step 5 — Validation

## 5.1 Active Directory Users and Computers (ADUC)
📁 Place into:  
`screenshots/5_validation/`
- active directory users and computers and dns.png  

## 5.2 DNS Resolution Tests
📁 Place into:  
`screenshots/5_validation/`
- test dns resolution.png  

## 5.3 Event Viewer Logs
📁 Place into:  
`screenshots/5_validation/`
- event logs.png  
- event logs better.png  

---

# 🟤 Step 6 — Organizational Units, Users, and Groups

## 6.1 Organizational Unit Creation
OU: `David_Admins`

📁 Place into:  
`screenshots/6_ou_user_group_creation/`
- organizational units.png  

## 6.2 User Creation
📁 Place into:  
`screenshots/6_ou_user_group_creation/`
- created a user inside david_admins organizational unit.png  
- put password A@123456789.png  
- added password A@1234.png  

## 6.3 Security Group Creation
Group: `David_Groups`

📁 Place into:  
`screenshots/6_ou_user_group_creation/`
- created group.png  

## 6.4 Final Verification
📁 Place into:  
`screenshots/6_ou_user_group_creation/`
- proof to show the user and the group was created and on the bottom left you can see the organizational unit called david_admins.png  

---

# 🎉 Deployment Completed

This project demonstrates:

- Windows Server preparation  
- AD DS and DNS role installation  
- Domain controller promotion  
- DNS zone verification  
- ADUC validation  
- OU, user, and group creation  

The environment represents a complete enterprise Active Directory deployment.
