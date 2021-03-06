---
id: 736vcwwe0zyksv1n2kgnhmc
title: 2020 2
desc: ''
updated: 1641449245517
created: 1641266581399
---


## 2021-2

- Download Arch ISO from [Archlinux.org](https://archlinux.org/download/)
- On a Windows machine download [Rufus](https://rufus.ie/en/)
  - Use Rufus to burn the ISO to a USB
  - This makes a bootable disk for bootstrapping the system
  - Settings as of 2021-10-25
    - ![Alt](assets/images/Pasted_image_20211025015639.png)
    - ![Alt](assets/images/Pasted_image_20211025015715.png)
- insert USB into machine
- [Helpful installation guide](https://wiki.archlinux.org/title/Installation_guide)
- in the computer setup menu change the boot order to boot from the USB as first priority
- Ensure UEFI mode is active and prefered, verify once on the CLI with: `ls /sys/firmware/efi/efivars`
- Connect over wifi using `iwctl` 
  - Interactive Mode (These menus have Tab completion)
    - First, if you do not know your wireless device name, list all Wi-Fi devices: `[iwd]# device list`
    - Then, to scan for networks: `[iwd]# station <device> scan`
    - You can then list all available networks: `[iwd]# station <device> get-networks`
    - Finally, to connect to a network: `[iwd]# station <device> connect <SSID>`
  - Single Command with passed values: `iwctl --passphrase <passphrase> station <device> connect <SSID>`
- **AT THIS STAGE YOU CAN JUST RUN THE ARCHINSTALL SCRIPT AND CALL IT DONE AFTERWARDS**
- check accuracy of system clock: `timedatectl set-ntp true`
- See drives `lsblk`
- Partition drives with `cfdisk`
  - `[new] -> 600M [enter] -> [type] -> EFI -> [enter]`
  - `[new] -> 2xRAM in GB [enter] -> [type] -> Linux Swap -> [enter]`
  - `[new] -> 25G [enter] -> [type] -> Linux File System -> [enter]`
  - `[new] -> THE REST in GB [enter] -> [type] -> Linux File System -> [enter]`
  - `[write]`
  - `yes -> [enter]`
  - `[quit]`
- Write the EXT4 file system to the partitions and FAT32 for EFI 
  - `mkfs.fat -F32 /dev/sda1`
  - `mkfs.ext4 /dev/sda3`
  - `mkfs.ext4 /dev/sda4`
- Activate your swap partition
  - `mkswap /dev/sda2`
  - `swapon /dev/sda2`
- Mount your partitions to `/mnt`
  - `mount /dev/sda3 /mnt` &lt;&lt;- mounting the root
    - `mkdir /mnt/home`
      - `mount /dev/sda4 /mnt/home`
    - `mkdir /mnt/boot`
      - `mount /dev/sda1 /mnt/boot`
- bootstrap the system with some initial packages and software
  - `pacstrap /mnt base base-devel vim networkmanager grub linux linux-firmware man-db man-pages texinfo`
- generate an fstab file
  - `genfstab /mnt`
  - `genfstab -U /mnt >> /mnt/etc/fstab`
  - `vim /mnt/etc/fstab`
- root access into the new system `arch-chroot /mnt`
- activate network manager `systemctl enable NetworkManager`
- set the timezone `In -sf /usr/share/zoneinfo/America/Los_Angeles /etc/localtime`
- Run hwclock to generate /etc/adjtime: `hwclock --systohc`
- localization: `vim /etc/locale.gen` un-comment the `en_US` items
- run `locale-gen`
- `vim /etc/locale.conf` add: "LANG=en_US.UTF-8"
- `vim /etc/hostname` put name of machine here (i.e. what do you want your computers name to be)
- set password for ROOT account `passwd`
- enable microcode updates?? `initrd=\cpu_manufacturer-ucode.img initrd=\initramfs-linux.img`
- setup boot loader
  - `grub-install --target=i386-pc /dev/sda`
  - `grub-mkconfig -o /boot/grub/grub.cfg`
- exit the chroot environment `exit`
- unmount all partitions `umount -R /mnt`
- reboot the system `reboot`
  - while reboot is occurring remove the bootable USB
  - Login to the system as the root user
