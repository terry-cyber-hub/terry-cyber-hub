#  Practicing Using System Recovery Options

Quick reference guide for systems administration concepts, commands, and best practices.

## Windows Command Line

### Registry Commands
```
regedt32.exe          # Launch Registry Editor
regedit.exe           # Alternative Registry Editor
```

### Key Registry Paths
- **HKEY_LOCAL_MACHINE (HKLM)** - Local computer settings, applies to all users
- **HKEY_CURRENT_USER (HKCU)** - Settings specific to logged-in user
- **HKEY_CLASSES_ROOT** - File type associations and COM classes
- **HKEY_USERS** - All user profiles on system

### Safe Registry Navigation
1. Always launch as Administrator
2. Navigate, don't modify (when learning)
3. Use Ctrl+H to disable search highlighting if needed
4. Exit without saving unintended changes

## PowerShell Basics

### Essential Commands
```powershell
Get-Help           # Display command help
Get-Command        # List available commands
Get-Process        # List running processes
```

### User Management (prep)
- Will focus on creating, modifying, and removing local users
- Understanding user permissions and group policies

## Active Directory Concepts

### Key Definitions
- **Domain** - Logical grouping of users and computers
- **OU (Organizational Unit)** - Container for organizing objects
- **GPO (Group Policy Object)** - Rules for users and computers
- **LDAP** - Protocol for querying directory services

## Security & Permissions

### UAC (User Account Control)
- Prompts for elevated privileges on sensitive actions
- Can be configured but not recommended to disable
- Balance between security and usability

### NTFS Permissions
- Read (R) - View file contents
- Write (W) - Modify files
- Execute (X) - Run programs
- Modify (M) - Change files
- Full Control (FC) - All permissions

## Certification Roadmap

### CompTIA A+
- Core 1: Hardware, OS troubleshooting
- Core 2: Advanced OS, networking, security

### CompTIA Network+
- Network fundamentals, protocols, security

## Resources
- CompTIA A+ Study Guide

---

**Last Updated:** February 2026
