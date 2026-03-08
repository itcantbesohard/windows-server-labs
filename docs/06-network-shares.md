## 06 – Network Shares and Permissions
This section describes the creation and configuration of shared network folders in the szkola.local domain. Network shares allow users to store files centrally, collaborate, and access resources based on their role (students, teachers, administrators). Proper permission management ensures that each group has access only to the resources intended for them.

## Creating Shared Folders on the Server
Tasks performed
- Created a main directory on the server, for example:
C:\Shares\
- Inside this directory, created the following subfolders:
- Students
- Teachers
- Admins
- Public
- Right‑clicked each folder and selected Properties → Sharing → Advanced Sharing.
- Enabled Share this folder and assigned share names identical to folder names.
Expected results
- All folders are visible as network shares.
- Users can access shares according to their permissions.
- The server hosts a clean and organized share structure.
Screenshots
- Folder structure on the server
- Advanced Sharing window

Configuring NTFS Permissions
Tasks performed
- Opened Security tab for each folder.
- Assigned permissions based on security groups created earlier:
- Students_G → Read/Write access to Students folder.
- Teachers_G → Read/Write access to Teachers folder.
- Admins_G → Full control over all folders.
- Public → Read/Write access for all authenticated users.
- Removed Everyone group where necessary to avoid unintended access.
Expected results
- Students can access only the Students share.
- Teachers can access only the Teachers share.
- Admins have full control over all shares.
- Public share is accessible to all domain users.
Screenshots
(Add your screenshots here)
- NTFS permission settings
- Group assignments

## Configuring Share Permissions
Tasks performed
- Set share‑level permissions to:
- Everyone → Full Control (recommended when NTFS permissions are used to enforce security)
- Ensured that NTFS permissions, not share permissions, control access.
Expected results
- Access is managed consistently through NTFS rules.
- No conflicts between share and NTFS permissions.
Screenshots
(Add your screenshots here)
- Share permissions window

## Mapping Network Drives (Optional)
Tasks performed
- Used Group Policy Management to map drives automatically:
- Students → \\server\Students mapped as drive S:
- Teachers → \\server\Teachers mapped as drive T:
- Admins → \\server\Admins mapped as drive A:
- Public → \\server\Public mapped as drive P:
- Configured drive mapping under:
User Configuration → Preferences → Windows Settings → Drive Maps
Expected results
- Drives appear automatically when users log in.
- No manual configuration is required on client machines.
Screenshots
(Add your screenshots here)
- Drive mapping GPO settings
- Mapped drives visible on a client machine

## Testing Access from a Client Machine
Tasks performed
- Logged in as a student, teacher, and admin on a Windows 10 domain‑joined machine.
- Verified access to the appropriate shares.
- Attempted to open restricted folders to confirm access is denied.
- Tested file creation, modification, and deletion.
Expected results
- Students can access only the Students and Public shares.
- Teachers can access only the Teachers and Public shares.
- Admins can access all shares.
- Permissions behave consistently across all clients.

Screenshots
(Add your screenshots here)
- Access tests for each role
- Permission denied message (if applicable)

## Summary
Network shares have been successfully created and secured using NTFS and share permissions. Each user role now has access to the appropriate resources, and optional drive mapping ensures a smooth user experience. The environment is now ready for implementing logon scripts and additional automation in the next step of the lab.

Would you like me to prepare 07-logon-scripts.md next so your documentation stays consistent?
