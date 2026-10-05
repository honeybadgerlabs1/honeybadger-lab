# HoneyBadger Lab

Enterprise IT, cybersecurity, networking, and systems administration homelab portfolio maintained by **honeybadgerlabs1**.

## Overview

HoneyBadger Lab is a multi-system environment built to practice real-world desktop support, systems administration, networking, security monitoring, identity management, virtualization, and IT service management workflows.

## Lab Environment

| System | Purpose |
|---|---|
| Windows Server / HB-WIN-DC | Active Directory Domain Services, DNS, users, groups, Group Policy |
| HB-FILE-01 | Windows file services and departmental access control |
| Windows 11 endpoints | Domain clients and end-user support testing |
| OPNsense | Firewall, routing, and network security |
| Wazuh | SIEM, endpoint monitoring, and security visibility |
| GLPI | Help desk / ITSM, ticketing, LDAP authentication, technician workflows |
| Ubuntu/Linux | Linux administration and server services |
| Kali Linux | Authorized security testing and defensive lab exercises |
| VMware / Proxmox | Virtualization platforms used to host lab systems |

## Projects

1. [Active Directory](projects/01-active-directory/README.md)
2. [Group Policy](projects/02-group-policy/README.md)
3. [File Server](projects/03-file-server/README.md)
4. [OPNsense Firewall](projects/04-opnsense-firewall/README.md)
5. [Wazuh SIEM](projects/05-wazuh-siem/README.md)
6. [GLPI Help Desk](projects/06-glpi-helpdesk/README.md)
7. [Linux Server](projects/07-linux-server/README.md)
8. [Kali Security Lab](projects/08-kali-security/README.md)
9. [Remote Access](projects/09-remote-access/README.md)

## Skills Demonstrated

- Active Directory administration and LDAP integration
- DNS and Windows domain troubleshooting
- Group Policy configuration
- Role-based access control using security groups
- Windows file sharing and NTFS permissions
- ITSM ticket lifecycle and help-desk operations
- Linux administration
- SIEM deployment and endpoint monitoring
- Firewall and network administration
- PowerShell, Bash, and Python scripting
- Virtualization and multi-VM infrastructure
- Remote administration and troubleshooting

## Architecture

```text
                    HoneyBadger Lab
                          |
                    OPNsense Firewall
                          |
       +------------------+------------------+
       |                  |                  |
   HB-WIN-DC          Linux Systems      Security Systems
 AD DS / DNS              |                  |
       |               Ubuntu             Wazuh
       |                                    Kali
 +-----+---------+
 |               |
HB-FILE-01    Windows 11 Endpoints
 |               |
 |               +----------+
 |                          |
 +----------------------> GLPI
                         Help Desk
                         LDAP / AD
```

## Security Notice

This repository documents an isolated training environment. Credentials, private keys, API tokens, personally identifiable information, and sensitive operational information are intentionally excluded. Security testing is performed only against systems owned or explicitly authorized for use in the lab.

## Repository Owner

GitHub: **honeybadgerlabs1**
