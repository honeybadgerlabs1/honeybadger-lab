# Active Directory Lab

## Objective
Build and administer the `ad.honeybadgerlab.com` Windows domain.

## Work Completed
- Deployed Windows Server domain controller
- Installed Active Directory Domain Services and DNS
- Created organizational units for departments
- Created and managed domain users and security groups
- Joined Windows endpoints to the domain
- Practiced password resets, account state checks, and group membership administration
- Integrated Active Directory with other lab services such as GLPI

## Useful Commands
```powershell
Get-ADDomain
Get-ADDomainController
Get-ADUser -Filter *
Get-ADGroup -Filter *
Get-ADGroupMember "GroupName"
Get-ADPrincipalGroupMembership "username"
```
