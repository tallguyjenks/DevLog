---
id: IC0OT4PM5edoNbD5cbCeh
title: Ilo
desc: ''
updated: 1645349911828
created: 1645349901517
---

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
