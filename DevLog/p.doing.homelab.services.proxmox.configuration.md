---
id: ghqfq24dh7bjkpabdqvstm6
title: Configuration
desc: ''
updated: 1652072375716
created: 1643183994393
---

## Updates Repository

For regular updates and to avoid errors set the updates repository from the enterprise proxmox repo (subscription required) to the `pve-no-subscription` repo.

![repos](/assets/images/2022-01-25-23-37-43.png)

0. `pve node > updates > repositories`
1. disable the enterprise repo
2. `[Add]`
3. `pve-no-subscription`
4. run `apt-get update; apt dist-upgrade; reboot`

## Enable IOMMU

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
## Make Proxmox VLAN aware

1. go to `pve node > System > Network`
2. "Edit" your Linux bridge
3. check the box for `VLAN aware:`
4. Click `Apply Configuration`

This will update `/etc/network/interfaces` with new settings and where it says `bridge-vids` you can change the default `2-4094` to be a single number for the [[terms.vlan]] of the server, or do that for individual virtual machines

## Setup Linux Bridge for Virtual Machines Separate from management Layer

1. `pve node > System > Network > Create > Linux Bond`
2. `bond0`
3. List all the bridge ports in a space separated list except the 1 used for the management layer
4. choose [[n.ieee-802.3ad]] mode for [[n.protocol.lacp]]
5. Add Comment
6. after finished creating modify switch side settings for [[n.protocol.lacp]] for those ports

### Make Network Bridge for Virtual Machines

- <https://youtu.be/qTbeHpdHcqs>

1. `pve node > System > Network > Create > Linux Bridge`
2. `vmbr1` is fine
3. Give it a IPV4 address like `10.10.10.0/24`
4. make it `VLAN aware:`
5. List all the bridge ports in a space separated list (the [[n.protocol.lacp]] `bond0` you made)
6. Add Comment

## Setup NFS for backups

0. You need to have the [[terms.nfs]] share already setup so [[p.doing.homelab.servers.fafnir]] needs to already be setup and mounted to the proxmox instance?
1. `Datacenter node > storage > add > nfs`
2. `ID` ==> "Backups"
3. Server IPV4 address (address to [[p.doing.homelab.servers.fafnir]]?)
4. Export `/mnt/storage <++>`

### Schedule Backups

1. `Datacenter node > backup > add`
2. Select Node to backup
3. Select storage share to send backups to
4. Schedule Backups
5. Email notification Settings
6. Compression level (ZSTD)
7. mode == snapshot
8. test it
   1. make a backup immediately

## Download Windows VirtIO drivers

1. Go To [This page](https://pve.proxmox.com/wiki/Windows_VirtIO_Drivers)
2. Click the link under `Installation` for downloading latest stable release
3. upload iso to proxmox iso's in `local > ISO images > Upload`

## Configure Email notifications

Change `/etc/postfix/main.cf` to include/change these lines:

```txt
relayhost = [smtp.gmail.com]:587
smtp_use_tls = yes
smtp_sasl_auth_enable = yes
smtp_sasl_security_options = noanonymous
smtp_sasl_password_maps = hash:/etc/postfix/sasl_passwd
smtp_tls_CAfile = /etc/ssl/certs/ca-certificates.crt

#mydestination = $myhostname, localhost.$mydomain, localhost
```

Be sure there are no dupes as the `main.cf` may have `smtp_sasl_security_options = {}` , and `relayhost = {}`. Just delete or comment those lines.

Create an `/etc/postfix/sasl_passwd` file with:

```txt
[smtp.gmail.com]:587    testmehere@gmail.com:PASSWD
```

run

```bash
chmod 600 /etc/postfix/sasl_passwd
postmap /etc/postfix/sasl_passwd
```

install for passwd support:

```bash
apt-get install libsasl2-modules
```

Restart service:

```bash
systemctl restart postfix.service
```

Test:

```bash
echo "Test mail from postfix" | mail -s "Test Postfix" test@test.com
```

Test from PVE:

```bash
echo "test" | /usr/bin/pvemailforward
```

## Setup port forwarding for RDP to windows VM's and make VM's visible on the internal network:

1. Start a shell from the web console
2. edit `/etc/network/interfaces`
3. make it look like:

```bash
auto vmbr1
iface vmbr1 inet static
        address 10.1.10.0/24
        bridge-ports bond0
        bridge-stp off
        bridge-fd 0
        bridge-vlan-aware yes
        bridge-vids 20
        post-up echo 1 > /proc/sys/net/ipv4/ip_forward
        post-up iptables -t nat -A POSTROUTING -s '192.168.0.0/24' -o vmbr0 -j MASQUERADE
        post-down iptables -t nat -D POSTROUTING -s '192.168.0.0/24' -o vmbr0 -j MASQUERADE    
        iptables -t nat -A PREROUTING -i bond0 -p tcp --dport 13389 -j DNAT --to 192.168.3.15:3389
#VM Net
```

## Setup iperf3 on the server

```bash
apt-get install iperf3
```

In the `~/.profile` file, add this line:

```bash
iperf3 -s &
```

this will make it so upon server startup iperf3 will be run as an independant process that can can gather data from.

By default it listens on port [[n.port.5021]]
