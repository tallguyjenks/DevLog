
## Resources

- [Manual](assets/pdfs/hp-dl360p-g8-manual.pdf)

## Hardware

- [Information on iLO][1]
- [TO BUY for more memory some day][3]

## Services

- Running [[p.doing.homelab.services.proxmox]]

## Projects

- [reorganizing hardware with m.2 for OS][2]
  - [This advice for mirroring the boot drives][4]

## Post menus

### First Menu

- <kbd>F8</kbd> iLO 4 advanced
- <kbd>F9</kbd> setup
- <kbd>CTRL</kbd> + <kbd>S</kbd> enter Ethernet Boot Agent Configuration Menu

### Second Menu

- <kbd>F5</kbd> Smart Storage Administrator
- <kbd>F8</kbd> Run the Option ROM Configuration For Arrays Utility
- <kbd>ESC</kbd> Skip Configuration and Continue
- <kbd>CTRL</kbd> + <kbd>C</kbd> to start the Avago utility

### Third Menu

- <kbd>F9</kbd> ROM-Based Setup Utility (same as <kbd>F9</kbd> in Menu One)
- <kbd>F10</kbd> Intelligent Provisioning (can access menus to get to Storage Admin, diagnostics, RBSU utility, etc)
- <kbd>F11</kbd> Default Boot Override Options
- <kbd>F12</kbd> Network Boot

---

[1]: https://en.wikipedia.org/wiki/HP_Integrated_Lights-Out
[2]: https://www.reddit.com/r/homelab/comments/t5na4v/comment/hz66dwy/?utm_source=share&utm_medium=web2x&context=3
[3]: https://www.ebay.com/itm/222462491975?hash=item33cbcc3d47:g:Ks4AAOSwNZRfLGSf
[4]: https://forum.proxmox.com/threads/installation-with-m-2-ok.58009/
