---
id: so9y5z1c2e7sjgzgh583ap9
title: Troubleshooting
desc: ''
updated: 1649033875090
created: 1649033508110
---

## Issue with unable to add drives to a ZFS Pool 

> [EFAULT] Failed to wipe disk da14: [Errno 22] Invalid argument

> I just want to add my thanks to the OP for creating and particularly to swissroot for the link that made it all come together.
>
> I bought 6 4Tb Seagate drives from a recycler thinking that I could just plug them into my Dell T620 bays and load them up as mirrored vdevs. Its a new build that I'm playing with and while I waited for my H220 flashed to LSI HBA from The Art of Server, I noticed that the H710P raid card could see all the devices but only one was open and usable and five were marked as 'blocked'. That is a well-documented issue that should be fixed by updating the firmware of the card but mine wasn't playing ball. I figured that the H220/LSI would see the drives and make them available when I installed it.
>
> No bueno! The H220 could see the drives but at 0.00Gb; at least I could format them through the BIOS interface for the H220 if only one at a time and 15 hours each. I thought that was the end of the issue but I suspected it might not be.
>
> Fast forward, all got formatted through the H220, I fired up TrueNAS core and it could see all the drives but threw an error when I tried to create the vdevs. Searching that error brought me to this thread and the link provided by swissroot provided the info I needed to sg_format the drives in parallel to a 512 byte sector rather than 520 byte.
>
> For those reading this with the same issue, what I've learned so far is that used HDD are often good value but if they have been used in Netapp/EMC hardware, they need to be mounted on an HBA (not a raid card) and re-formatted to 512 byte sectors in order for them to work and be mounted as useable drives in Freenas/Truenas.
>
> The reason this is pretty unique and hard to track down is that it seems to be an issue that is limited or confined to situations where drives that have been used in other storage arrays that utilise 520 bytes sectors are used in equipment that is looking for 512 byte sectors.
