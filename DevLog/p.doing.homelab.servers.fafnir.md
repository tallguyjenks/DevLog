---
id: 1lpaxh3d5akybf5ql65q070
title: Fafnir
desc: Dell PowerEdge R720
updated: 1646726565184
created: 1641018811979
---


ACTIVE
TODO add info on the hardware, ports, etc

## Resources

- [Hardware info][1]
- [Installing the OS][2]
  - [Getting around bootable USB issue][3]
- [This upgrade][0]
  - [further notes][4]

## Installation

- Running [[p.doing.homelab.services.truenas]]
- View [[p.doing.homelab.servers.fafnir.idrac]] interface in firefox
  - Set console to be HTML5
- Load .iso virtual media to the CD/ROM
- `F11` to open UEFI manager
- change boot order and select boot device
  - select `Virtual Media Optical Disk`
- Install with the minimal prompts to the 2 mirrored SSD's
- Reboot
- Change the boot order to now boot from the SSD's first
- Boot into TrueNAS
- Begin Configuration

[0]: https://dan.langille.org/2019/10/05/preparing-the-dell-r720-for-zfs/
[1]: https://qrl.dell.com/Product/Detail/3
[2]: https://www.dell.com/support/kbdoc/en-il/000130160/how-to-install-the-operating-system-on-a-dell-poweredge-server-os-deployment
[3]: https://www.truenas.com/community/threads/dell-poweredge-r720-boot-problem.21259/
[4]: https://gist.github.com/dlangille/cd784830cd7fb00c63744dfac1dd2e16
