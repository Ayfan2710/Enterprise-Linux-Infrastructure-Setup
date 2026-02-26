# Enterprise Linux Infrastructure Setup and Hardening

This project demonstrates the complete setup and hardening of an enterprise-level Linux server using RHEL 9.  

The objective was to simulate a real-world production environment by configuring secure remote access, firewall policies, logical volume management (LVM), network file sharing (NFS), and system service management.

This project reflects hands-on system administration skills aligned with RHCSA-level competencies and enterprise infrastructure best practices.

---

## Technologies Used

- RHEL 9
- LVM (Logical Volume Manager)
- SSH (Secure Remote Access)
- Firewalld
- NFS (Network File System)
- Systemctl
- SELinux

---

## Project Goals

- Configure and secure SSH with key-based authentication
- Implement firewall rules to control network traffic
- Create and manage logical volumes using LVM
- Configure NFS server for centralized file sharing
- Apply basic system hardening practices
- Validate configuration using real-world testing methods

---

## Infrastructure Overview

- Single RHEL 9 server deployed on VMware
- Dedicated LVM disk for storage management
- Secure SSH login using key authentication
- Firewall rules configured using firewalld
- NFS service configured and tested locally

---

##  Documentation

Detailed configuration steps are available below:

- [SSH Hardening](docs/SSH-Hardening.md)
- [Firewall Configuration](docs/Firewall-Configuration.md)
- [LVM Implementation](docs/LVM-Implementation.md)
- [NFS Setup](docs/NFS-Setup.md)
- [System Security & Hardening](docs/System-Security.md)

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

---

## Architecture Summary

- VMware Virtual Machine running RHEL 9
- Dedicated LVM storage disk
- SSH secured with key authentication
- Firewalld controlling network access
- NFS server providing shared storage
- SELinux enforcing security policies

This architecture simulates a small-scale enterprise Linux infrastructure environment.

---

##  Lessons Learned

- Importance of layered security (Firewall + SELinux + SSH hardening)
- Benefits of LVM for scalable storage management
- Practical experience managing Linux services with systemctl
- Understanding of secure file sharing using NFS
- Improved troubleshooting skills through log monitoring

This project strengthened hands-on Linux administration capabilities aligned with RHCSA-level skills.
