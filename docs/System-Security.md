# System Security and Hardening Practices

##  Objective

To apply essential system security and hardening practices on a RHEL 9 server to reduce vulnerabilities and improve overall system integrity.

This step focuses on enterprise-level best practices.

---

##  Environment

- Operating System: RHEL 9
- SELinux enabled
- firewalld configured
- SSH hardened

---

##  Step 1 – Verify SELinux Status

Checked SELinux mode:

getenforce

Confirmed system running in:

Enforcing mode

## Step 2 – Keep System Updated

Updated system packages:

sudo dnf update -y

Ensures latest security patches are applied.

## Step 3 – User and Permission Management

Avoided direct root login

Used non-root administrative user

Applied proper file permissions

Restricted unnecessary directory access

Checked permissions:

ls -l

## Step 4 – Log Monitoring

Reviewed system logs using:

sudo journalctl -xe

Checked SSH login attempts:

sudo journalctl -u sshd

Monitoring logs helps detect suspicious activity.

## Step 5 – Service Management

Listed running services:

systemctl list-units --type=service

Disabled unnecessary services when not required.

## Step 6 – Password Policy Awareness

Checked password aging policy:

sudo chage -l alice

Ensured password management follows good security practices.

## Step 7 – Secure File Permissions

Example:

chmod 600 sensitive_file

Ensures only authorized users can access critical files.


## Validation

1. SELinux running in enforcing mode

2. System updated with latest patches

3. SSH hardened

4. Firewall active

5. Logs reviewed for anomalies

## Security Improvements Achieved

1. Reduced attack surface

2. Improved authentication security

3. Enforced access control policies

4. Applied enterprise Linux hardening fundamentals
