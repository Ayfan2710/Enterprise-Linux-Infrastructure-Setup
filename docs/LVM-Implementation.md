# LVM (Logical Volume Manager) Implementation

##  Objective

To implement flexible storage management using LVM in RHEL 9. 
The goal was to create scalable storage volumes that can be resized dynamically without downtime.

---

##  Environment

- Operating System: RHEL 9
- Additional Virtual Disk attached
- Storage managed using LVM

---

##  Step 1 – Verify New Disk

Checked available disks:


lsblk

Verified new disk (example: /dev/sdb).

## Step 2 – Create Physical Volume
sudo pvcreate /dev/sdb

Verified:

sudo pvs

##  Step 3 – Create Volume Group
sudo vgcreate data_vg /dev/sdb

Verified:

sudo vgs

##  Step 4 – Create Logical Volume

Created 5GB logical volume:

sudo lvcreate -L 5G -n data_lv data_vg

Verified:

sudo lvs

##  Step 5 – Format Logical Volume
sudo mkfs.xfs /dev/data_vg/data_lv

##  Step 6 – Create Mount Point
sudo mkdir /data

Mounted volume:

sudo mount /dev/data_vg/data_lv /data

Verified:

df -h
##  Step 7 – Make Mount Persistent

Edited fstab:

sudo nano /etc/fstab

Added:

/dev/data_vg/data_lv   /data   xfs   defaults   0 0

Tested:

sudo mount -a

##  Step 8 – Extend Logical Volume

Extended by 2GB:

sudo lvextend -L +2G /dev/data_vg/data_lv
sudo xfs_growfs /data

Verified new size:

df -h

##  Validation

1. Logical volume created successfully

2. Mounted storage accessible

3. Data persists after reboot

4. Volume resized without downtime

## Benefits of LVM

1. Flexible storage management

2. Easy resizing of volumes

3. Better storage organization

4. Enterprise-grade storage handling
