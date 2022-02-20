---
id: ACirxEkc5V7njTYEDwTGP
title: Confirguration
desc: ''
updated: 1645381703004
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
