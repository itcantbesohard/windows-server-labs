# 02 – Installing Active Directory Domain Services (AD DS)
This section covers the installation and configuration of Active Directory Domain Services on Windows Server 2012. The goal is to promote the server to a Domain Controller and create the domain szkola.local, which will be used throughout the lab.

## Installing the AD DS Role
Tasks performed
- Opened Server Manager.
- Selected Add roles and features.
- Chose Role-based or feature-based installation.
- Selected Active Directory Domain Services.
- Confirmed required features and completed the installation.
Expected results
- AD DS role installed successfully.
- Server Manager displays a notification to promote the server to a Domain Controller.
Screenshots
(Add your screenshots here)
- AD DS role installation wizard
- Installation p

## Promoting the Server to a Domain Controller
Tasks performed
- Clicked Promote this server to a domain controller in Server Manager.
- Selected Add a new forest.
- Entered the domain name: szkola.local.
- Set the Forest Functional Level and Domain Functional Level to Windows Server 2012.
- Enabled DNS Server option.
- Set the Directory Services Restore Mode (DSRM) password.
- Completed the configuration wizard and restarted the server.
Expected results
- Server becomes the first Domain Controller in the forest.
- Domain szkola.local is created.
- DNS service is automatically installed and configured.
Screenshots
(Add your screenshots here)
- Domain creation wizard
- DSRM password screen
- Post‑restart confirmation

## Verifying AD DS Installation
Tasks performed
- Opened Active Directory Users and Computers (ADUC).
- Confirmed the presence of the default domain structure.
- Checked DNS Manager to ensure zones were created correctly.
- Verified that the server appears as a Domain Controller in Active Directory Sites and Services.
Expected results
- Domain szkola.local visible in ADUC.
- Forward Lookup Zone created automatically.
- Server listed as a Domain Controller.
Screenshots
(Add your screenshots here)
- ADUC domain tree
- DNS zone view
- Domain Controller listing

## Summary
At this stage, the server is fully promoted to a Domain Controller for the szkola.local domain. Active Directory and DNS are operational, and the environment is ready for creating Organizational Units, users, and groups in the next step of the lab.