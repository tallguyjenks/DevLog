---
id: c9xl709kyecyyy01t1sxw6m
title: 2020 1
desc: ''
updated: 1641266567536
created: 1641266567536
---


## 2020-1

```bash
timedatectl set-ntp true
ping lukesmith.xyz
wifi-menu
cfdisk
[new] -> 600M [enter] -> [type] -> EFI -> [enter]
[new] -> 2xRAM in GB [enter] -> [type] -> Linux Swap -> [enter]
[new] -> 25G [enter] -> [type] -> Linux File System -> [enter]
[new] -> THE REST in GB [enter] -> [type] -> Linux File System -> [enter]
[write]
yes -> [enter]
quit
mkfs.ext4 /dev/sda1
mkfs.ext4 /dev/sda3
mkfs.ext4 /dev/sda4
mkswap /dev/sda2
swapon /dev/sda2
mount /dev/sda3 /mnt                        # mounting the root
mkdir /mnt/home
mkdir /mnt/boot
mount /dev/sda1 /mnt/boot
mount /dev/sda4 /mnt/home
pacstrap /mnt base base-devel vim
genfstab /mnt
genfstab -U /mnt >> /mnt/etc/fstab
vim /mnt/etc/fstab
arch-chroot /mnt
pacman -S networkmanager
systemctl enable NetworkManager
pacman -S grub
grub-install --target=i386-pc /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg
passwd
vim /etc/locale.gen #uncomment the en_US items
locale-gen
vim /etc/locale.conf # add: "LANG=en_US.UTF-8"
ln -sf /usr/share/zoneinfo/America/los-angelas /etc/localtime
vim /etc/hostname # put name of machine here
exit
umount -R /mnt
reboot

#~=============================~
#AFTER LARBS NETWORK MANAGEMENT
#~=============================~

sysctl net.ipv4.tcp_ecn=0
```
