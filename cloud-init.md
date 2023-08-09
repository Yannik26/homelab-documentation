---
title: Clout Init
nav_order: 0
layout: page
---
# Cloud Init
Instructions to setup a cloud init template on proxmox

## Get a cloud init ready image
For example for debian: [Debian Cloud](https://cloud.debian.org/images/cloud/)
Image: debian-xx-generic-amd64-xxxxxx.raw
Download the image into your /tmp folder on your proxmox machine with wget

## Setup virtual machine
Create a empty virtual machine:
    qm create _<id>_
Import the raw disk into your vm:
    qm importdisk _<id>_ debian-xx-generic-amd64-xxxxx.raw local-lvm
In the PVE webinterface:
Reference the imported disk as scsi, set disk as bootable, add a network device,setup Uefi,add a cloud-init disk, eable qemu-guest-agent
