# 03 – DNS Configuration
This section describes the DNS configuration that is automatically created during the promotion of the Windows Server 2012 machine to a Domain Controller. DNS is a critical component of Active Directory, as domain joins, authentication, and service discovery rely on proper name resolution.

## DNS Role Overview
Active Directory requires DNS to function correctly. When the server was promoted to a Domain Controller in the previous step, the DNS Server role was installed automatically. The domain szkola.local now has its own DNS zone, which stores records for domain controllers, clients, and AD services.
Key DNS components created automatically
- Forward Lookup Zone for szkola.local
- SOA and NS records
- Host (A) record for the Domain Controller
- SRV records for AD services (LDAP, Kerberos, GC)

## Verifying DNS Zones
Tasks performed
- Opened DNS Manager from Server Manager.
- Expanded Forward Lookup Zones.
- Confirmed the presence of the szkola.local zone.
- Checked automatically generated records:
- SOA (Start of Authority)
- NS (Name Server)
- A record for the Domain Controller
- SRV records under _msdcs, _sites, _tcp, _udp
Expected results
- The szkola.local zone exists and contains all required AD-related records.
- The Domain Controller appears with the correct IP address.
- No errors or warnings in DNS Manager.
Screenshots
(Add your screenshots here)
- DNS Manager main view
- Forward Lookup Zone contents
- SRV record folders

## Testing DNS Resolution
Tasks performed
- Used nslookup on the server and client to verify name resolution.
- Queried the domain name and Domain Controller hostname.
- Ensured the client uses the server’s IP as its DNS server.
Example commands

```
nslookup szkola.local
nslookup servername.szkola.local
```

Expected results
- Queries return the correct IP address of the Domain Controller.
- No timeout or “Non-existent domain” errors.

Screenshots
(Add your screenshots here)
- nslookup results on server
- nslookup results on client

## Common Issues and Fixes
Missing SRV records
Often caused by:
- Incorrect DNS IP on the client
- Server not pointing DNS to itself
- DNS service not running
Incorrect IP in A record
Occurs when:
- Server IP was changed after promotion
- DHCP assigned a new address
Fix:
- Update the A record manually or restart the Netlogon service.

## Summary
DNS is now fully configured and operational for the szkola.local domain. The Forward Lookup Zone contains all required AD records, and both the server and client can resolve domain names correctly. With DNS functioning properly, the environment is ready for creating Organizational Units, users, and groups in the next step.


