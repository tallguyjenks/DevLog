---
id: ACirxEkc5V7njTYEDwTGP
title: Confirguration
desc: ''
updated: 1645382571310
created: 1643183994393
---

## Configuration

### Updates Repository

For regular updates and to avoid errors set the updates repository from the enterprise proxmox repo (subscription required) to the `pve-no-subscription` repo.

![repos](/assets/images/2022-01-25-23-37-43.png)

1. disable the enterprise repo
2. `[Add]`
3. `pve-no-subscription`

### Enable IOMMU

Enable [[terms.iommu]] so VM's can access hardware not made for virtualization (GPU's etc.)

1. you can do this but updating the `/etc/default/grub` file
   - change `GRUB_CMDLINE_LINUX_ DEFAULT="quiet"`
   - to: `GRUB_CMDLINE LINUX DEFAULT="quiet intel iommu=on"`
2. Then run `update-grub`
3. Then edit `/etc/modules`

Add these 4 lines to it:

```txt
`vfio`
`vfio_iommu_typel`
`vfio_pci`
`vfio_virqfd`
```

Then Reboot

### Make Proxmox VLAN aware

1. go to `System > Network`
2. "Edit" your Linux bridge
3. check the box for `VLAN aware:`

This will update `/etc/network/interfaces` with new settings and where it says `bridge-vids` you can change the default `2-4094` to be a single number for the [[terms.vlan]] of the server, or do that for individual virtual machines

### Setup NFS for backups

0. You need to have the [[terms.nfs]] share already setup so [[p.doing.homelab.servers.fafnir]] needs to already be setup and mounted to the proxmox instance?
1. `Datacenter node > storage > add > nfs`
