# 01 – Environment Setup
This section describes the preparation of the virtual environment used for the Windows Server 2012 and Windows 10 school domain lab. The goal is to create a clean, isolated setup where the server will act as the domain controller for szkola.local, and Windows 10 machines will operate as domain clients.

## Virtual Machine Setup
Machines used
- Windows Server 2012
Role: Domain Controller (AD DS, DNS)
- Windows 7
Role: Client machine (student/teacher/admin profiles)
Tasks performed
- Created two virtual machines in VirtualBox.
- Assigned appropriate resources (CPU, RAM, disk).
- Configured both machines to use the same internal/host‑only network.
Screenshots
(Add your screenshots here)
- VM settings
- Network configuration

## Network Configuration
Server (Windows Server 2012)
- Assigned a static IP address
- Configured subnet mask and gateway
- Set DNS to point to itself (server IP)
Client (Windows 7)
- Configured to obtain IP automatically or set manually within the same subnet
- DNS set to the server’s IP (required for domain join)
Example configuration
- Server: 10.0.0.1
- Client: 10.0.0.10
- Subnet: 255.255.255.0
- DNS: 
Screenshots:
[ipconfig on server](screenshots/server-ipconfig.png)
[ipconfig on client](screenshots/client-ipconfig.png)

## Backup Configuration
- Configured Windows Server Backup
- Full system backup
- Schedule: daily at 21:00
- Backup target: separate volume on the same physical disk
Screenshots
[backup schedule](screenshots/backup-schedule.png)
- Backup target volume

## Connectivity Testing
Tasks performed
- Verified that both machines can communicate using ping.
- Ensured no firewall rules block ICMP or domain communication.
Expected results
- Successful ping from client → server
- Successful ping from server → client
Screenshots:
[ping on server](screenshots/server-ping.png)
[ping on client](screenshots/client-ping.png)

## Summary
At this stage, the environment is ready for installing Active Directory Domain Services. Both machines are connected, the server has a static IP, and the client can reach the server using DNS. This forms the foundation for the next steps in the lab.