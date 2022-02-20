---
id: j6rUprJFPtgMVGY331LC3
title: Ymir
desc: 'HP Prolient DL360p G8'
updated: 1645348945580
created: 1641018533079
---

ACTIVE

- TODO <https://youtu.be/LxdCzfF77t4>
    - ILO port and configuration
      - Make sure the iLO port is connected to a port on the switch that is on the same VLAN as the remote device attempting to connect to it.
      - you can let DHCP handle DORA and configuration and then boot from virtual media via iLO
      - Booting from virtual media is an option in the `F9` menu that needs to be enabled before attempting iLO boot
    - iLO from scratch
      - enter iLO menu with `F8` after POST
      - in the `[file]` option there is a reset to default settings
      - as long as the above points are handled then you can get a new DHCP DORA process going so that you can use intelligent provisioning via `F10` to boot from an `.iso` on the remote machine.
      - **NOTE:** to use the virtual media install you need an iLO license, a trial license should work just fine

- Troubleshooting Fresh [[p.doing.homelab.proxmox]] install
    - Stack Overflow Posts
        - [Is there a better workaround or solution to boot a Proliant DL380 Gen8 from USB DVD drive than "Restore Default System Settings"?][1]
        - [Resetting factory defaults - HP Proliant DL360 gen8][2]
- [Information on iLO][3]

[1]: https://serverfault.com/questions/556775/is-there-a-better-workaround-or-solution-to-boot-a-proliant-dl380-gen8-from-usb
[2]: https://serverfault.com/questions/662448/resetting-factory-defaults-hp-proliant-dl360-gen8?noredirect=1&lq=1
[3]: https://en.wikipedia.org/wiki/HP_Integrated_Lights-Out
