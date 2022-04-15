---
id: p4mog8mu5oi3u7tg97iwjb4
title: Setup
desc: ''
updated: 1650006098499
created: 1643183976632
---


## Proxmox setup steps

0. [Great installation video](https://youtu.be/azORbxrItOo)
1. [download iso](https://proxmox.com/en/downloads)
2. Burn iso to a flashdrive
   1. linux: `dd` command
   2. Windows: [rufus](https://rufus.ie/en/)
   3. MacOS: [Etcher](https://www.balena.io/etcher/)
3. Put flash drive into target machine
4. Boot from the flash drive
   1. or using [[p.doing.homelab.servers.ymir.ilo]]
5. Follow the prompts and fill in the information
   1. Note: i did have to configure my disks in some of the boot menus to make a single logical volume RAID 5 configuration
   2. The in the Proxmox installer i just selected ext4 for the file system
   3. Will use ZFS on [[p.doing.homelab.servers.fafnir]]
6. fill in network information
   1. Much of it can be gleaned from your router console
   2. `ifconfig get default | grep gateway` for the default gateway
   3. for MacOS to find [[n.protocol.dns]] server just search for `DNS` in *system preferences*
7. Once proxmox is finished bootstrapping and restarts the server, remove the flash media
8. if screen loads to a console then you can just transition back to your main machine and use the web interface to finish.
9. management console is at: `https://#.#.#.#:8006` (replace `#` with valid IPV4 address)
10. connection will be insecure and that's okay, proceed anyhow
11. login as `root` with the password you previously set.
12. Ignore subscription popup, its FOSS unless you want enterprise subscription

## Post Install Configuration

TODO reformat this section by separating out the steps to their own notes and making this list more legible

1. [[p.doing.homelab.services.proxmox.configuration#updates-repository]]
2. `apt-get install neovim ranger`
3. [[p.doing.homelab.services.proxmox.configuration#enable-iommu]]
4. [[p.doing.homelab.services.proxmox.configuration#make-proxmox-vlan-aware]]
5. [[p.doing.homelab.services.proxmox.configuration#setup-linux-bridge-for-virtual-machines-separate-from-management-layer]]
   1. [[p.doing.homelab.services.proxmox.configuration#make-network-bridge-for-virtual-machines]]
6. [[p.doing.homelab.services.proxmox.configuration#download-windows-virtio-drivers]]
7. [[p.doing.homelab.services.proxmox.configuration#setup-nfs-for-backups]]
   1. [[p.doing.homelab.services.proxmox.configuration#schedule-backups]]
