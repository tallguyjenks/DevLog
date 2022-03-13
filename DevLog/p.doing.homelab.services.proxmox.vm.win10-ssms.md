---
id: ti26wzo0a48fbzkasuq69lj
title: Win10 Ssms
desc: ''
updated: 1647133194844
created: 1645393642980
---


TODO go through this video and actually write out the steps with pictures too on what to set up

<https://youtu.be/6c-6xBkD2J4>

1. Download [Windows 10 iso][0] (64bit)
2. Download the Latest [virtio-win iso][1]
3. upload the iso's to [[p.doing.homelab.services.proxmox]]
4. Create new VM in Proxmox
   1. General
      1. Give it a name 
      2. ![General](/assets/images/2022-03-12-16-52-44.png)
   2. OS
      1. Select windows iso
      2. guest type to windows
      3. version 10 
      4. ![OS](/assets/images/2022-03-12-16-53-32.png)
   3. System
      1. Turn on QEMU Agent 
      2. ![System](/assets/images/2022-03-12-16-54-16.png)
   4. Hard Disk
      1. Bus/Device --> SCSI
      2. Storage --> your choice
      3. Disk Size --> 60GB?
      4. Cache --> Write back
      5. ![hard disk](/assets/images/2022-03-12-16-56-29.png)
   5. CPU
      1. Cores --> 24?
      2. ![CPU](/assets/images/2022-03-12-16-57-19.png)
   6. Memory
      1. Balooning (use minimum 1GB max 8GB)
      2. Memory (MiB) --> 8192
      3. Minimum memory (MiB) --> 1024
      4. ![Memory](/assets/images/2022-03-12-16-58-55.png)
   7. Network
      1. Model --> VirtIO (paravirtualized)
      2. ![Network](/assets/images/2022-03-12-16-59-42.png)
   8. 

[0]: https://www.microsoft.com/en-us/software-download/windows10ISO
[1]: https://docs.fedoraproject.org/en-US/quick-docs/creating-windows-virtual-machines-using-virtio-drivers/index.html
