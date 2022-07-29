
## Installation

Helpful Resource: <https://youtu.be/psVNn-JVT9Q>

1. View [[p.doing.homelab.servers.fafnir.hardware.idrac]] interface in firefox
   1. Set console to be HTML5
2. Load .iso virtual media to the CD/ROM
3. `F11` to open UEFI manager
4. change boot order and select boot device
   1. select `Virtual Media Optical Disk`
5. Install with the minimal prompts to the 2 mirrored SSD's
6. Reboot
7. Change the boot order to now boot from the SSD's first
8. Boot into TrueNAS
9. Begin [[p.doing.homelab.services.truenas.configuration]]
