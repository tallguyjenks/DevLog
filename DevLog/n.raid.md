---
id: mep0uxfj8cg7vokezmzxgf4
title: Raid
desc: ''
updated: 1647123987750
created: 1643181270670
---


TODO flesh out these notes

<https://www.acronis.com/en-us/articles/whats-raid10-and-why-should-i-use-it/>
<https://en.wikipedia.org/wiki/Standard_RAID_levels>
<https://www.techrepublic.com/article/understand-when-raid-60-is-overkill/>
<https://www.ionos.com/digitalguide/server/security/raid-6/>

## RAID

> Redundant Array of Independent Disks

- Is not a backup
  - If your operating system or software, rather than the hard disk, corrupts your data, this corrupted data is sent to both disks and simultaneously corrupts both drives.

### RAID 0

- ![RAID 0, 1, and 10 Example](/assets/images/2022-03-12-14-20-16.png)
- Striping (Disk A and B contain data split between them that together forms the whole)

### RAID 1

- ![RAID 0, 1, and 10 Example](/assets/images/2022-03-12-14-20-16.png)
- Mirroring (Disk A and B are exact copies of each other)

### RAID 5

- 

### RAID 6

<++>

### RAID 10

- ![RAID 0, 1, and 10 Example](/assets/images/2022-03-12-14-20-16.png)
- Combination of [RAID 0](#raid-0) and [RAID 1](#raid-1)
- Requires at least 4 drives
- Protects you from a single drive failure
  - reads the surviving mirror and stores the copy to the new drive you replaced. (A heavy load for the surviving disk and potential failure point of the 2nd disk)
- cuts your usable disk space in half 4x2TB Disks == 4TB total storage

### RAID 50

<++>

### RAID 60
