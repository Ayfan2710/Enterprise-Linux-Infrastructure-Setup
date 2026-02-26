# NFS (Network File System) Setup

##  Objective

To configure NFS server on RHEL 9 to enable centralized file sharing across systems within the network.

This simulates enterprise shared storage access.

---

##  Environment

- Operating System: RHEL 9
- NFS Server and Client configured on same VM (local testing)
- Firewall configured to allow NFS service

---

## Step 1 – Install NFS Utilities

sudo dnf install nfs-utils -y

## Step 2 – Start and Enable NFS Service
sudo systemctl start nfs-server
sudo systemctl enable nfs-server

Verify:

systemctl status nfs-server

## Step 3 – Create Shared Directory

sudo mkdir -p /shared
sudo chmod 777 /shared

## Step 4 – Configure Exports File

Edit:

sudo nano /etc/exports

Add:

/shared  *(rw,sync,no_root_squash)

## Step 5 – Apply Export Configuration

sudo exportfs -rav

Verify:

sudo exportfs -v

##  Step 6 – Allow NFS in Firewall

sudo firewall-cmd --permanent --add-service=nfs
sudo firewall-cmd --reload

## Step 7 – Test NFS Mount (Local Testing)

Create mount directory:

sudo mkdir /mnt/nfs-test

Mount:

sudo mount localhost:/shared /mnt/nfs-test

Test file creation:

touch /mnt/nfs-test/testfile.txt
ls /shared

If file appears → NFS working successfully.

##  Validation

1. NFS service active

2. Shared directory exported

3. Mount successful

4. File access verified

5. Firewall configured properly

##  Security Considerations

1. Restricted export rules in production environments

2. Avoided public access in real enterprise setup

3. Firewall controls implemented
