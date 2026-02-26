# Firewall Configuration Using firewalld

## 📌 Objective

To configure and manage firewall rules using firewalld in RHEL 9 to control network access and enhance server security.

The goal was to allow only required services while blocking unnecessary traffic.

---

## 🔧 Environment

- Operating System: RHEL 9
- Firewall Service: firewalld
- Virtualized on VMware Workstation

---

## 🔥 Step 1 – Verify Firewall Status

Checked firewall service:

systemctl status firewalld

Started and enabled firewall:

sudo systemctl start firewalld
sudo systemctl enable firewalld

Verified status:

firewall-cmd --state
##  Step 2 – Check Active Zone

firewall-cmd --get-active-zones

Listed all rules:

firewall-cmd --list-all

##  Step 3 – Allow Required Services

Allowed SSH service permanently:

sudo firewall-cmd --permanent --add-service=ssh

Allowed NFS service:

sudo firewall-cmd --permanent --add-service=nfs

Reloaded firewall:

sudo firewall-cmd --reload

## Step 4 – Block Unnecessary Ports

Example of blocking specific port:

sudo firewall-cmd --permanent --remove-port=8080/tcp
sudo firewall-cmd --reload

##  Step 5 – Verify Configuration
firewall-cmd --list-all

Confirmed only required services were allowed.

## Validation

1. SSH access works through firewall

2. NFS traffic allowed

3. Unauthorized ports blocked

4. Firewall persists after reboot

## Security Improvements

1. Restricted open ports

2. Reduced attack surface

3. Enforced service-based firewall rules

4. Applied permanent rule configuration
