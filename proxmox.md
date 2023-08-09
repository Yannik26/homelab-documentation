---
title: Proxmox
nav_order: 0
layout: page
---
# Proxmox PVE
## Download
Download newest version at [proxmox.com](https://www.proxmox.com/de/downloads)

## Prepare Boot Medium
Burn the downloaded iso onto a USB stick or similar with dd
    dd if=_path/to/iso_ of=_path/of/usb/stick_ status=progress
After writing finished plug the usb stick into your machine and boot from the stick

## Installation
Follow the guided installer and set yor values. after that reboot your machine.

## First Boot/Config
Add proxmox no-subscription repo via _<your hostname> -> Updates -> Repositories_
Click Add Repository and choose **No-Subscription**
Disable the enterprise Repositories

## OVS Networking
This step is fully optional. Follow if you want to use OVS (Open Virtual Switch)
1. Install the package openvswitch-switch by running:
    apt install openvswitch-switch
2. In the Network Page remove the vmbr0 bridge
3. Create a new OVS Bridge. Coose a name you like. Here I will use vmbr0. In the field Bridge Ports enter the name of your physical network port
4. Create a OVS IntPort. Choose a name, enter your network data and choose the right OVS Bridge
5. Repeat this for your VLANs
6. Apply the config


