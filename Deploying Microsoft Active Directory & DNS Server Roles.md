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




---

## 1.2 Configure a Static IP Address
A domain controller requires a static IP address to remain reachable.

***IP Address Configuration Explanation***

For this deployment, the following values are entered:

Let’s put this for our IP address:


```
192.168.1.100
```

Let’s put this for our subnet mask:


```
255.255.255.0
```


Let’s put this for our default gateway:


```
192.168.1.1
```

***Why these values are used***

192.168.1.100 — IP Address

This address is selected because:

It matches the network being used (192.168.1.x)

It does not fall inside the DHCP range, preventing address conflicts

It provides the domain controller with a reliable and consistent network identity

Active Directory services depend on the server keeping the same address, so clients can always reach it

This IP address becomes the server’s permanent point of contact on the network.



---


255.255.255.0 — Subnet Mask

This subnet mask is used because:

It defines the network as 192.168.1.0/24

Devices within this range can communicate with each other

It follows common LAN configurations used in both home labs and small business networks

This ensures all devices in the 192.168.1.x range are recognized as part of the same local network.

---


192.168.1.1 — Default Gateway

This gateway address is used because:

It is the router’s address on the local network

It handles communication going outside the 192.168.1.x range

It provides internet access and routes traffic beyond the LAN

The server sends all non-local traffic to the gateway at 192.168.1.1.

---

**Screenshots:** 

<img width="1148" height="812" alt="image" src="https://github.com/user-attachments/assets/a350072e-40cd-4ac7-b59d-72543d3fba51" />

---

The IP settings now show DHCP is off, meaning the server uses a fixed IP address that never changes, ensuring stable domain services.


<img width="1110" height="815" alt="image" src="https://github.com/user-attachments/assets/1f87c399-ff6d-42dd-97d0-fe20fffd9a0b" />


These images show IPv4 settings configured manually, confirming that DHCP is not assigning the server’s IP.

---

## 1.3 Hostname & Server Manager
**Screenshot:**  

<img width="1130" height="836" alt="image" src="https://github.com/user-attachments/assets/0ec682f7-3a24-4e87-b939-fb07f400eacd" />


This confirms the hostname and displays Server Manager, the main interface for managing server roles.

---

## 1.4 Network Connectivity Verification
**Screenshots:**  

<img width="1102" height="813" alt="image" src="https://github.com/user-attachments/assets/e04f3e0b-ede4-4ba1-b574-5445c76d8ebb" />

---

<img width="1143" height="837" alt="image" src="https://github.com/user-attachments/assets/fd4bd55a-d655-4d19-aa42-41f0ea99becd" />



These images display `ping` tests confirming communication with:

- The local gateway  
- External internet hosts  

---

## 1.5 Windows Server Updates
**Screenshot:**  

<img width="1107" height="798" alt="image" src="https://github.com/user-attachments/assets/742fb2b3-d55a-4d00-991c-0799cfee132a" />





Displays Windows Update or PowerShell-based update commands.

---

# Step 2 — Install Active Directory and DNS Roles

## 2.1 Open Server Manager
**Screenshot:**  

<img width="1147" height="845" alt="image" src="https://github.com/user-attachments/assets/49d18f02-ae66-4a30-8d7a-299d6d8b8346" />


Shows navigation to the “Add roles and features” wizard.

---

## 2.2 Add Roles and Features Wizard
**Screenshots:**  

<img width="1182" height="818" alt="image" src="https://github.com/user-attachments/assets/e315792d-9584-46de-ba74-ccd2e4f471bf" />

---

<img width="1160" height="850" alt="image" src="https://github.com/user-attachments/assets/8984e140-61b8-453d-9897-4aeb7a3224a7" />

---

<img width="1173" height="831" alt="image" src="https://github.com/user-attachments/assets/cc53294d-8d51-4c45-9e1e-9c5c13b12ed3" />

---

<img width="1301" height="828" alt="image" src="https://github.com/user-attachments/assets/99311f10-9b9f-4271-8973-2d1b230affcd" />


These images show the full process for selecting:

- AD DS  
- DNS Server  
- Required supporting features  

---

# Step 3 — Promotion to Domain Controller

## 3.1 Begin Promotion
**Screenshot:**

<img width="1260" height="847" alt="image" src="https://github.com/user-attachments/assets/655b2a3c-61d8-4bbb-a0ce-29927e4665dd" />

Shows the post-deployment notification used to start domain controller promotion.

---

## 3.2 Create New Forest & Domain
Domain created:

```
david.local
```

**Screenshot:**  

<img width="1253" height="862" alt="image" src="https://github.com/user-attachments/assets/44352b92-f2cc-4e17-bf41-c514d10a72bd" />


Shows the root domain name entry.

---

## 3.3 Domain Controller Options
**Screenshot:**  

<img width="1127" height="800" alt="image" src="https://github.com/user-attachments/assets/ab81fea3-1136-4d79-8dfb-d88285183384" />


Displays forest/domain functional levels, DNS server selection, Global Catalog, and DSRM password creation.

---

## 3.4 Prerequisite Check & Review
**Screenshots:**  


<img width="955" height="781" alt="image" src="https://github.com/user-attachments/assets/a7aab9a2-6efa-406c-8f35-919c05b278dd" />

---

<img width="1217" height="841" alt="image" src="https://github.com/user-attachments/assets/4aaeae49-6c39-4ed4-ba0a-b0e8fa661039" />



Confirm valid configuration and readiness for domain controller promotion.

---

# Step 4 — DNS Configuration

## 4.1 Role Verification
**Screenshot:**  


<img width="1162" height="815" alt="image" src="https://github.com/user-attachments/assets/e0fcda78-83f7-4df6-879c-847cfd3f5836" />


Shows AD DS and DNS roles installed successfully.

---

## 4.2 Lookup Zone Verification
**Screenshot:**  

<img width="1162" height="805" alt="image" src="https://github.com/user-attachments/assets/14fc9b52-5415-40a6-8ec5-f9161b9416e2" />


Shows the Forward Lookup Zone, reverse lookup zone container, and `_msdcs` domain records.

---

# Step 5 — Validation

## 5.1 ADUC (Active Directory Users and Computers)
**Screenshot:**  

<img width="1222" height="826" alt="image" src="https://github.com/user-attachments/assets/3961f5c9-e044-4f87-a929-0bc269bbf8a5" />


Confirms the domain structure loaded correctly.

---

## 5.2 DNS Resolution Tests
**Screenshot:** 

<img width="1158" height="821" alt="image" src="https://github.com/user-attachments/assets/2248bad2-bcf3-423e-8567-5b82fd17cbb6" />



Shows `nslookup` and `ping` resolving the domain name and reaching the domain controller IP.

---

## 5.3 Event Viewer Logs
**Screenshots:**  

<img width="1146" height="826" alt="image" src="https://github.com/user-attachments/assets/e359b49a-ae28-4a9a-b546-85209d5a3ce0" />

---

<img width="1270" height="847" alt="image" src="https://github.com/user-attachments/assets/6a73b3c7-c64a-4076-9da3-6249cad270fc" />



Displays system and directory service logs confirming no critical errors.

---

# Step 6 — Organizational Units, Users, and Groups

## 6.1 Create an Organizational Unit
OU created:

```
David_Admins
```

**Screenshot:**  

<img width="1176" height="822" alt="image" src="https://github.com/user-attachments/assets/e1f00d84-b536-4de0-8f21-07fae3060aae" />


---

## 6.2 Create a User
**Screenshots:**  

<img width="1231" height="827" alt="image" src="https://github.com/user-attachments/assets/94484cbc-39a3-4246-a753-583c8dcb2c7a" />

---

<img width="1202" height="827" alt="image" src="https://github.com/user-attachments/assets/014493ae-d0d6-40a1-97ae-185bb40bda7c" />


 

Show a user account created within the OU.

---

## 6.3 Create a Security Group
Group name:

```
David_Groups
```

**Screenshot:**  

<img width="1211" height="827" alt="image" src="https://github.com/user-attachments/assets/d9b67dbc-819c-422f-a503-d55b9787a301" />



---

## 6.4 Final Verification
**Screenshot:**  

<img width="1210" height="847" alt="image" src="https://github.com/user-attachments/assets/c4281f1d-0be0-491e-9d13-1d2bca1cb466" />
  

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

