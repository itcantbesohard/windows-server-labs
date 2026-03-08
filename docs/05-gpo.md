# 05 – Group Policy Objects (GPO)
This section describes the creation and configuration of Group Policy Objects (GPOs) for the szkola.local domain. GPOs allow centralized management of user and computer settings. In this lab, policies are applied to different Organizational Units (OUs) to reflect the roles in a school environment: students, teachers, and administrators.

## Purpose of GPOs in This Environment
Group Policy is used to:
- Restrict or allow access to system features.
- Configure desktop environments for different user roles.
- Apply security settings.
- Map network drives and logon scripts.
- Enforce consistent behavior across all domain‑joined machines.
The goal is to create a controlled environment for students, a more flexible one for teachers, and an administrative environment for IT staff.

## Creating GPOs for Each OU
Tasks performed
- Opened Group Policy Management.
- Created the following GPOs:
- Students_GPO – applied to the Students OU.
- Teachers_GPO – applied to the Teachers OU.
- Admins_GPO – applied to the Admins OU.
- Linked each GPO to the corresponding OU.

Expected results
- Each OU has its own dedicated GPO.
- Policies apply only to users within the targeted OU.
- No cross‑OU policy inheritance unless explicitly configured.

Screenshots
(Add your screenshots here)
- GPO list in Group Policy Management
- GPO linked to OU

## Example Settings for Students
Tasks performed
- Disabled access to Control Panel.
- Blocked command prompt.
- Restricted access to system settings.
- Configured a custom desktop background (optional).
- Disabled the ability to install software.

Expected results
- Students have a limited and controlled environment.
- System tools and administrative features are hidden or blocked.
- Desktop experience is consistent across all student accounts.

Screenshots
(Add your screenshots here)
- Control Panel restriction
- Command prompt restriction

## Example Settings for Teachers
Tasks performed
- Allowed access to Control Panel (basic settings only).
- Enabled access to printers and network shares.
- Configured folder redirection (optional).
- Allowed use of some administrative tools (e.g., Task Manager).
Expected results
- Teachers have more flexibility than students.
- They can manage classroom resources without full administrative rights.
- Their environment remains secure but functional.
Screenshots
(Add your screenshots here)
- Teacher GPO settings
- Folder redirection (if used)

## Example Settings for Admins
Tasks performed
- Granted full access to administrative tools.
- Enabled PowerShell and Command Prompt.
- Allowed installation of software.
- Ensured no restrictive policies apply to administrators.
Expected results
- Admin accounts have full control over the domain environment.
- No restrictions interfere with management tasks.

Screenshots
(Add your screenshots here)
- Admin GPO settings
- Administrative tools enabled

## Tasks performed
- Logged in as a student, teacher, and admin on a Windows 10 domain‑joined machine.
- Ran gpupdate /force to apply policies.
- Verified that each role receives the correct restrictions or permissions.
Expected results
- Students see a restricted environment.
- Teachers have moderate access.
- Admins have full access.
Screenshots
(Add your screenshots here)
- gpupdate results
- User environment after GPO application

## Summary
GPOs have been successfully created and applied to the appropriate OUs. Each user role now has a tailored environment that reflects its responsibilities and permissions within the school domain. The next step in the lab will focus on configuring shared network resources and assigning permissions based on the security groups created earlier.
