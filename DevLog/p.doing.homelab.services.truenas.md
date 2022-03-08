---
id: 8uwug8f8zbnr2gzb163euk2
title: TrueNAS
desc: ''
updated: 1646727222054
created: 1641324520480
---

TODO <https://youtu.be/psVNn-JVT9Q>

## Installation

- View [[p.doing.homelab.servers.fafnir.hardware.idrac]] interface in firefox
  - Set console to be HTML5
- Load .iso virtual media to the CD/ROM
- `F11` to open UEFI manager
- change boot order and select boot device
  - select `Virtual Media Optical Disk`
- Install with the minimal prompts to the 2 mirrored SSD's
- Reboot
- Change the boot order to now boot from the SSD's first
- Boot into TrueNAS
- Begin [[p.doing.homelab.services.truenas.configuration]]
