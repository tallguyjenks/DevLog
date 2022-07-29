---
id: p4mog8mu5oi3u7tg97iwjb4
title: Setup
desc: ''
updated: 1659123606540
created: 1643183976632
---


## Proxmox setup steps

0. [Great installation video](https://youtu.be/azORbxrItOo)
1. [download iso](https://proxmox.com/en/downloads)
2. Use management interface on the server, [[p.doing.homelab.servers.fafnir.hardware.idrac]]
   1. Turn server on
   2. Attach virtual media (the .iso)
3. Follow the prompts and fill in the information
   1. chose [[n.raid#raid-z]]1 for a mirrored boot drive on SSD pair
      1. if SSD's are not visible on boot, check that the SATA settings in device settings is set to ACHI and auto
4. fill in network information
   1. Much of it can be gleaned from your router console
   2. `ifconfig get default | grep gateway` for the default gateway
   3. for MacOS to find [[n.protocol.dns]] server just search for `DNS` in *system preferences*
5. Once proxmox is finished bootstrapping and restarts the server, remove the virtual media
6. if screen loads to a console then you can just transition back to your main machine and use the web interface to finish.
7. management console is at: `https://#.#.#.#:8006` (replace `#` with valid IPV4 address)
8. connection will be insecure and that's okay, proceed anyhow
9. login as `root` with the password you previously set.
10. Ignore subscription popup, its FOSS unless you want enterprise subscription

## Post Install Configuration

TODO reformat this section by separating out the steps to their own notes and making this list more legible

1. `apt-get install neovim ranger tldr`
2. [[p.doing.homelab.services.proxmox.configuration]]
