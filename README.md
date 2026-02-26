# Enterprise Linux Infrastructure Setup and Hardening

## Project Overview

This project demonstrates the complete setup, configuration, and hardening of an Enterprise Linux server using RHEL 9. The objective of this project was to simulate a real-world production server environment and apply security best practices, storage management, service configuration, and automation techniques.

The project covers Linux administration tasks commonly expected from a System Administrator or DevOps Engineer.

---

## Technologies Used

- Red Hat Enterprise Linux 9
- LVM (Logical Volume Manager)
- SSH (Key-based Authentication)
- Firewalld
- NFS (Network File System)
- Bash Scripting
- Systemctl
- SELinux

---

## Project Implementation

### 1. User Management and SSH Hardening
- Created non-root administrative user
- Configured SSH key-based authentication
- Disabled password authentication
- Restricted root login
- Tested secure remote access

### 2. Firewall Configuration
- Configured firewalld zones
- Opened required service ports
- Permanently applied firewall rules
- Verified active services

### 3. LVM Storage Management
- Added additional disk
- Created Physical Volume
- Created Volume Group
- Created Logical Volumes
- Formatted and mounted storage
- Configured persistent mount using /etc/fstab

### 4. NFS Configuration
- Installed NFS utilities
- Configured export directories
- Managed NFS service
- Verified remote mounting functionality

### 5. SELinux Enforcement
- Verified enforcing mode
- Managed SELinux contexts
- Ensured secure service access

---

## Screenshots

Screenshots of implementation steps are available inside the screenshots directory.

---

## Key Skills Demonstrated

- Enterprise Linux Administration
- System Hardening
- Storage Management (LVM)
- Network Services Configuration
- Firewall and Security Management
- Automation with Bash
- Troubleshooting and Debugging

---

## Conclusion

This project reflects hands-on practical experience in managing and securing a Linux server environment similar to production infrastructure. It demonstrates both system administration fundamentals and real-world troubleshooting skills.


---

## Project Screenshots

### SSH Key-Based Authentication
![SSH Screenshot](screenshots/ssh-login.png)

### Firewall Configuration
![Firewall Screenshot](screenshots/firewall.png)

### LVM Storage Setup
![LVM Screenshot](screenshots/lvm-setup.png)

### NFS Server Configuration
![NFS Screenshot](screenshots/nfs-status.png)
