---
id: ghqfq24dh7bjkpabdqvstm6
title: Configuration
desc: ''
updated: 1646373894119
created: 1643183994393
---

## Configuration

### Updates Repository

For regular updates and to avoid errors set the updates repository from the enterprise proxmox repo (subscription required) to the `pve-no-subscription` repo.

![repos](/assets/images/2022-01-25-23-37-43.png)

1. disable the enterprise repo
2. `[Add]`
3. `pve-no-subscription`
4. run `apt-get update; apt dist-upgrade; reboot`

### Enable IOMMU

<!-- markdownlint-disable MD031-->

Enable [[terms.iommu]] so VM's can access hardware not made for virtualization (GPU's etc.)

1. you can do this but updating the `/etc/default/grub` file
   - change `GRUB_CMDLINE_LINUX_ DEFAULT="quiet"`
   - to: `GRUB_CMDLINE LINUX DEFAULT="quiet intel iommu=on"`
2. Then run `update-grub`
3. Then edit `/etc/modules` Add these 4 lines to it:
4.  
   ```txt
   `vfio`
   `vfio_iommu_typel`
   `vfio_pci`
   `vfio_virqfd`
   ```
5. Then run `update-initramfs -u -k all`
6. reboot

<!-- markdownlint-enable MD031-->
### Make Proxmox VLAN aware

1. go to `System > Network`
2. "Edit" your Linux bridge
3. check the box for `VLAN aware:`
4. Click `Apply Configuration`

This will update `/etc/network/interfaces` with new settings and where it says `bridge-vids` you can change the default `2-4094` to be a single number for the [[terms.vlan]] of the server, or do that for individual virtual machines

### Setup NFS for backups

TODO This setup

0. You need to have the [[terms.nfs]] share already setup so [[p.doing.homelab.servers.fafnir]] needs to already be setup and mounted to the proxmox instance?
1. `Datacenter node "> storage > add > nfs`
2. `ID` ==> "Backups"
3. Server IPV4 address (address to [[p.doing.homelab.servers.fafnir]]?)
4. Export `/mnt/storage <++>`

#### Schedule Backups

1. `Datacenter node > backup > add`
2. Select Node to backup
3. Select storage share to send backups to
4. Schedule Backups
5. Email notification Settings
6. Compression level (ZSTD)
7. mode == snapshot
8. test it
   1. make a backup immediately

### Setup Linux Bridge for Virtual Machines Separate from management Layer

1. `pve node > System > Network > Create > Linux Bond`
2. `bond0`
3. Give it a IPV4 address
4. List all the bridge ports in a space separated list
5. choose [[n.ieee-802.3ad]] mode for [[n.protocol.lacp]]
6. Add Comment

#### Make Network Bridge for Virtual Machines

- <https://youtu.be/qTbeHpdHcqs>

1. `pve node > System > Network > Create > Linux Bridge`
2. `vmbr1` is fine
3. Give it a IPV4 address
4. make it `VLAN aware:`
5. List all the bridge ports in a space separated list
6. Add Comment

### Download Windows VirtIO drivers

1. Go To [This page][1]
2. Click the link under `Installation` for downloading latest stable release
3. upload iso to proxmox iso's in `local > ISO images > Upload`

[1]: https://pve.proxmox.com/wiki/Windows_VirtIO_Drivers
