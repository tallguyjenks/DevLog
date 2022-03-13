---
id: ti26wzo0a48fbzkasuq69lj
title: Win10 Ssms
desc: ''
updated: 1647134933603
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
   8. Confirm
      1. Click Finish but do not start VM yet you need to configure 1 more thing
   9. VirtIO Virtual Disk
      1. We need to install the virtIO drivers to this VM
      2. therefore need to give the VM a disk drive to load the virtual disk into
      3. Select the VM in the proxmox panel
      4. Select the `Hardware` sub menu
      5. Click `Add > CD/DVD Drive`
      6. ![add drive](/assets/images/2022-03-12-17-02-41.png)
      7. Bus/Device --> IDE and 1
      8. Storage --> your choice
      9. Select the VirtIO iso file
      10. ![virtual disk](/assets/images/2022-03-12-17-03-46.png)
5. Click on the `VM > Console`
6. Right click `VM > Start`
7. follow allow with the normal installation of windows
8. can continue on without product key for reduced functionality mode
9. Select Custom install
    1. No hard drives found to install windows onto, need to load drivers from virtio
    2. Click `Load Driver`
    3. ![load driver](/assets/images/2022-03-12-17-06-28.png)
    4. click `Browse`
    5. ![browse](/assets/images/2022-03-12-17-07-09.png)
    6. Go to virtio disk and expand
    7. ![expand](/assets/images/2022-03-12-17-07-35.png)
    8. First install vioscsi
    9. ![vioscsi](/assets/images/2022-03-12-17-08-39.png)
    10. `vioscsi > w10 > amd64 > OK`
    11. ![amd64](/assets/images/2022-03-12-17-09-22.png)
    12. Click `Next`
    13. Now we can see the hard drive
    14. ![hard drive](/assets/images/2022-03-12-17-10-06.png)
    15. Click `Load Driver`
    16. ![load driver](/assets/images/2022-03-12-17-06-28.png)
    17. click `Browse`
    18. Go to virtio disk and expand
    19. ![expand](/assets/images/2022-03-12-17-07-35.png)
    20. `NetKVM > w10 > amd64`
        1. downloads network adapter drivers so we can get upgrades while installing
    21. ![netkvm](/assets/images/2022-03-12-17-15-03.png)
    22. Click `Next`
    23. Click `Load Driver`
    24. ![load driver](/assets/images/2022-03-12-17-06-28.png)
    25. click `Browse`
    26. Go to virtio disk and expand
    27. ![expand](/assets/images/2022-03-12-17-07-35.png)
    28. `Balloon > w10 > amd64`
    29. ![balloon](/assets/images/2022-03-12-17-17-15.png)
    30. Click `Next`
10. Now ready to continue with windows installation
11. Click `Next`
12. choose location
13. keyboard layout
14. personal use
15. offline account
16. name the pc
17. password
18. security questions
19. choose privacy settings (uncheck everything)
20. windows is running
21. go to `Device Manager`
22. Double click missing driver under `Other Devices`
    1. ![Other Devices](/assets/images/2022-03-12-17-20-23.png)
    2. Click `Update Driver...`
    3. Browse my computer for driver software
    4. Browse to the virtio disk and select it
    5. Click `OK`
    6. When prompted click `Install` to install the driver
23. Need to install the Guest Agent
    1. Go to `This PC`
    2. Enter the `virtio disk > guest-agent`
    3. Execute `qemu-ga-x86_64`
    4. Click `Yes` to install
    5. reboot
24. Click on `VM > Summary` See that guest agent isn't running because windows hasn't booted yet
25. Enter the Console
26. Boot the VM
27. once booted check on the guest-agent has an IP
28. Done!
29. BONUS
    1. For faster performance can activate Remote Desktop and just RDP onto the VM for near native performance

[0]: https://www.microsoft.com/en-us/software-download/windows10ISO
[1]: https://docs.fedoraproject.org/en-US/quick-docs/creating-windows-virtual-machines-using-virtio-drivers/index.html
