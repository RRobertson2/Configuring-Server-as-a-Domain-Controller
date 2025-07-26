# Configuring-Server-as-a-Domain-Controller

### Objective
This project demonstrates the deployment of a Windows Server 2022 virtual machine on a Proxmox hypervisor using a Dell PowerEdge T130 server. The goal was to configure the server as a domain controller and establish a new Active Directory domain. This hands-on experience highlights fundamental skills in Windows Server management, Active Directory setup, and virtualization.

### Skills Learned
- Configuration of Windows Server 2022 as a domain controller
- Installation and deployment of Active Directory Domain Services (AD DS)
- Understanding domain naming conventions and forest structure
- Implementation of Active Directory Certificate Services
- Familiarity with DSRM, NetBIOS, and certification authority configuration

### Tools Used
- Proxmox Virtual Environment
- Dell PowerEdge T130 Server
- Windows Server 2022
- Active Directory Domain Services (AD DS)
- Active Directory Certificate Services (AD CS)
- Server Manager
<br>

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">
  
### Step 1: Rename the Server for Domain Role
Renamed the default server hostname to DC01 to establish a standardized naming convention for domain controllers (e.g., DC01, DC02, etc.).

Assigning meaningful names improves organization and scalability in multi-domain environments. Renaming the server triggered a system restart to apply the changes.

<img src="https://github.com/user-attachments/assets/df59ae48-cfca-4c58-8082-848054164f20" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/be731d26-0e73-485b-9554-7fc185ee8f7b" width="1000">

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">

### Step 2: Begin Domain Controller Configuration
Initiated the installation of domain controller features using Add Roles and Features from the Server Manager dashboard.

Role-Based and Feature-Based Installation: This option allows you to install Windows Server roles and features on the current VM.<br>
<br>
<img src="https://github.com/user-attachments/assets/23cbfa76-b77e-4e56-a9ff-91eeae51376d" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

Server Pool Selection: This means selecting the local or remote server you want to configure from a pool of available servers in the Server Manager.<br>
<br>

<img src="https://github.com/user-attachments/assets/327d00e6-d3ba-4020-9653-e619ef5faae6" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

Active Directory Domain Services (AD DS): This feature enables the creation and management of a centralized directory for user and computer authentication within a domain.<br>
<br>

<img src="https://github.com/user-attachments/assets/82f5fbc2-0a84-4e75-9030-dfc20c3d1736" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

All other roles were left at their default settings.<br>
<br>

<img src="https://github.com/user-attachments/assets/b91138f1-4f66-492f-9728-347f505481f8" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/7816feab-33a1-467e-aaa3-eeced06e3044" width="1000">


<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 3: Promote Server to Domain Controller
After installing AD DS, proceeded to promote the server to a domain controller.
Converts the standalone server into a domain controller responsible for managing user authentication and enforcing domain policies.<br>
<br>

<img src="https://github.com/user-attachments/assets/ee9ee536-ffa5-4685-98cf-cfb77d0e78c5" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

New Forest Creation: Used the internal domain name DOOM.local to establish a new forest, the topmost structure in AD hierarchy.<br>
<br>
<img src="https://github.com/user-attachments/assets/b1efd7d0-b3d6-4c41-b259-dcdff22867e4" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

Directory Services Restore Mode (DSRM) Password: This recovery password is used for restoring the domain controller in case of failure.<br>
<br>
<img src="https://github.com/user-attachments/assets/849de40a-c4e8-4cbe-8a53-e9b7876886ff" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">





