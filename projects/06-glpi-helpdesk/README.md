# GLPI Help Desk + Active Directory

## Objective

Deploy an enterprise-style help desk integrated with HoneyBadger Active Directory so domain users can authenticate to GLPI and receive permissions based on AD security-group membership.

## Implemented

- GLPI help-desk platform
- Active Directory LDAP authentication
- AD security groups: `GLPI-Users`, `GLPI-Technicians`, `GLPI-Admins`
- Automatic GLPI authorization rules
- Self-Service, Technician, and Super-Admin profile mapping
- Incident creation and categorization
- Technician assignment
- Active Directory password-reset workflow
- Resolution notes and ticket closure

## Authorization Model

| Active Directory Group | GLPI Profile |
|---|---|
| GLPI-Users | Self-Service |
| GLPI-Technicians | Technician |
| GLPI-Admins | Super-Admin |

## Example AD Validation Commands

```powershell
Import-Module ActiveDirectory
Get-ADGroupMember "GLPI-Technicians"
Get-ADPrincipalGroupMembership "username" | Select-Object Name
Get-ADUser "username" -Properties MemberOf
```

## Password Reset Workflow

```powershell
$user = "username"
Get-ADUser $user -Properties Enabled,LockedOut,PasswordExpired

$newPassword = Read-Host "Enter temporary password" -AsSecureString
Set-ADAccountPassword -Identity $user -Reset -NewPassword $newPassword
Set-ADUser -Identity $user -ChangePasswordAtLogon $true
```

Do not store real passwords in scripts, screenshots, tickets, or repositories.

## Validation

A test incident was submitted by a domain user, assigned to a Technician-profile account, remediated through Active Directory, documented in GLPI, and marked solved.

## Detailed Documentation

See `HoneyBadger_GLPI_Active_Directory_Help_Desk_Lab.pdf` in this folder.
