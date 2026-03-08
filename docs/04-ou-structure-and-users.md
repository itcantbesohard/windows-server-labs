# 04 – Organizational Unit Structure and User Accounts
This section describes the creation of Organizational Units (OUs) and user accounts within the szkola.local domain. The goal is to build a clear and logical structure that reflects the roles in a school environment: students, teachers, and administrators. This structure will later be used for applying Group Policy Objects (GPOs) and managing permissions.

## Creating the OU Structure
Tasks performed
- Opened Active Directory Users and Computers (ADUC).
- Created the following Organizational Units under the szkola.local domain:
- Students
- Teachers
- Admins
- Computers
- Ensured that OUs are used instead of default system containers (e.g., Users), so GPOs can be applied properly.
Expected results
- A clean and readable OU structure is visible in ADUC.
- Each user category has its own dedicated OU.
- Domain‑joined computers will be moved to the Computers OU.
Screenshots
(Add your screenshots here)
- OU structure in ADUC
- OU properties

## Creating User Accounts
Tasks performed
- Created user accounts in the Students OU, such as:
- student01
- student02
- Created user accounts in the Teachers OU:
- teacher01
- teacher02
- Created an administrative account in the Admins OU:
- admin01
- Set passwords and optionally enabled “User must change password at next logon”.
Expected results
- Each user has a domain account assigned to the correct OU.
- Accounts are ready for login on domain‑joined Windows 10 machines.
- Administrative accounts can manage the domain environment.

Screenshots
(Add your screenshots here)
- User creation wizard
- User list inside each OU
- User account properties

## Creating Security Groups
Tasks performed
- Created domain security groups:
- Students_G
- Teachers_G
- Admins_G
- Added users to their respective groups.
- Prepared groups for later use in permissions and GPO assignments.
Expected results
- Each user belongs to the correct security group.
- Groups can be used to manage access to shared folders and apply GPOs.

Screenshots
(Add your screenshots here)
- Group list in ADUC
- Group membership view

## Summary
The OU structure and user accounts have been successfully created. The environment is now ready for applying Group Policy Objects tailored to each role and for joining Windows 10 machines to the domain. The next step will focus on configuring GPOs to control the user experience and security settings.
