# SSH Hardening and Secure Remote Access

## Objective

To secure remote access to the RHEL 9 server by implementing SSH key-based authentication and disabling insecure login methods.

This ensures that only authorized users with valid SSH keys can access the system.

---

##  Environment

- Operating System: RHEL 9
- Virtualized on VMware Workstation
- Single-server infrastructure

---

##  Step 1 – Verify SSH Service

Checked SSH service status:

systemctl status sshd

Enabled and started service:

systemctl enable sshd
systemctl start sshd

##  Step 2 - ##  Step 1 – Verify SSH Service

useradd alice
passwd alice

Root login is avoided in enterprise environments for security reasons.

## Step 3 – Generate SSH Key Pair

On client system:

ssh-keygen

Generated:

Private key → ~/.ssh/id_rsa

Public key → ~/.ssh/id_rsa.pub

## Step 4 – Copy Public Key to Server

ssh-copy-id alice@server-ip

Tested login:

ssh alice@server-ip
Login successful without password.

## Step 5 – Disable Password & Root Login

Edited SSH configuration:

nano /etc/ssh/sshd_config

Modified:

PasswordAuthentication no
PermitRootLogin no

Restarted service:

systemctl restart sshd

## Validation

1. SSH login works using key authentication

2. Password login is disabled

3. Root login is blocked

4. Service verified using systemctl


## Security Improvements

1. Reduced brute-force attack risk

2. Enforced secure authentication method

3. Followed enterprise SSH best practices
