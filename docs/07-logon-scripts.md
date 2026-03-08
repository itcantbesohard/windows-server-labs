# 07 – Logon Scripts
This section describes the creation and deployment of logon scripts in the szkola.local domain. Logon scripts allow administrators to automate tasks that run each time a user signs in, such as mapping network drives, setting environment variables, or launching applications. In this lab, scripts are used to complement GPO‑based drive mappings and provide additional automation for students, teachers, and administrators.

## Purpose of Logon Scripts
Logon scripts help standardize the user environment by performing actions automatically at sign‑in. They are especially useful when:
- GPO Preferences are not sufficient or require additional logic.
- Different user groups need different drive mappings or settings.
- Administrators want to automate repetitive tasks.
Scripts can be written in Batch (.bat) or PowerShell (.ps1). In this lab, simple Batch scripts are used for compatibility.

## Creating the Logon Script Directory
Tasks performed
- Navigated to the SYSVOL directory on the Domain Controller:
C:\Windows\SYSVOL\sysvol\szkola.local\scripts\
- Created the following script files:
- students_logon.bat
- teachers_logon.bat
- admins_logon.bat
Expected results
- All script files are stored in the domain’s replicated scripts folder.
- Scripts are accessible to all domain users during logon.
Screenshots
(Add your screenshots here)
- SYSVOL scripts folder
- Script files visible in the directory

## Example Logon Script Content
Students script (students_logon.bat)
```
@echo off
net use S: \\server\Students
net use P: \\server\Public
```
Teachers script (teachers_logon.bat)
```
@echo off
net use T: \\server\Teachers
net use P: \\server\Public
```

Admins script (admins_logon.bat)
```
@echo off
net use A: \\server\Admins
net use P: \\server\Public
```

Expected results
- Drives are mapped automatically at logon.
- Users receive only the drives relevant to their role.
Screenshots
(Add your screenshots here)
- Script content in Notepad
- Successful drive mapping after logon

## Assigning Logon Scripts via GPO
Tasks performed
- Opened Group Policy Management.
- Edited the following GPOs:
- Students_GPO
- Teachers_GPO
- Admins_GPO
- Navigated to:
User Configuration → Policies → Windows Settings → Scripts (Logon/Logoff)
- Added the appropriate script for each group.
Expected results
- Each user group runs its assigned script at logon.
- Scripts execute automatically without user interaction.
Screenshots
(Add your screenshots here)
- Logon script assignment in GPO
- Script list window

## Testing Logon Scripts on a Client Machine
Tasks performed
- Logged in as a student, teacher, and admin on a Windows 10 domain‑joined machine.
- Verified that the correct drives were mapped.
- Checked gpresult /r to confirm GPO application.
- Ensured no errors appeared during logon.
Expected results
- Students receive S: and P: drives.
- Teachers receive T: and P: drives.
- Admins receive A: and P: drives.
- Scripts run silently and reliably.
Screenshots
(Add your screenshots here)
- Mapped drives in File Explorer
- gpresult output

## Summary
Logon scripts have been successfully created, stored in SYSVOL, and assigned through GPOs. Each user role now receives the correct network drives automatically at sign‑in, ensuring a consistent and functional environment. The next step in the lab focuses on monitoring and administrative tools to manage and troubleshoot the domain.




