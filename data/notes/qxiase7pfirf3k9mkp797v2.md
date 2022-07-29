
## RAID

> Redundant Array of Independent Disks

- Is not a backup
  - If your operating system or software, rather than the hard disk, corrupts your data, this corrupted data is sent to both disks and simultaneously corrupts both drives.

### RAID 0

- ![RAID 0](/assets/images/2022-03-12-15-04-25.png)
- Striping (Disk A and B contain data split between them that together forms the whole)

### RAID 1

- ![RAID 1](/assets/images/2022-03-12-15-02-23.png)
- Mirroring (Disk A and B are exact copies of each other)

### RAID 10

- ![RAID 0, 1, and 10 Example](/assets/images/2022-03-12-14-20-16.png)
- Combination of [[RAID 0|n.raid#raid-0]] and [[RAID 1|n.raid#raid-1]]
- Requires at least 4 drives
  - Drives should be identical (The disk geometry (number of heads, cylinders, etc.) is critical and it is strongly recommended NOT to use dissimilar disks.)
- Protects you from a single drive failure
  - reads the surviving mirror and stores the copy to the new drive you replaced. (Not nearly as taxing of an operation as [[RAID 5|n.raid#raid-5]])
- cuts your usable disk space in half 4x2TB Disks == 4TB total storage

### RAID 4

- ![RAID 4](/assets/images/2022-03-12-16-31-20.png)
- consists of block-level striping with a dedicated parity disk.
- As a result of its layout, RAID 4 provides good performance of random reads
- while the performance of random writes is low due to the need to write all parity data to a single disk

### RAID 5

- ![RAID 5](/assets/images/2022-03-12-15-10-33.png)
- When a drive fails
  - it needs to read everything on all the remaining drives to rebuild the new, replaced disk (A heavy load for the surviving disk and potential failure point of the 2nd disk)
- Storage Volume ((Number of hard drives - 1) x storage capacity of the smallest hard drive)
  - 3x1TB drives == 2TB storage, 3rd disk is for parity data
- Only at risk for failure if at least 2 drives fail simultaneously
  - That’s why, typically, an odd number of data carriers, i.e., three, five, seven, etc., is combined.

### RAID 6

- ![RAID 6](/assets/images/2022-03-12-14-49-20.png)
- Combines four or more hard drives into a single logical drive.
- Often referred to as “RAID 5 expansion”
- Striping (All data is divided into blocks and distributed evenly to the participating hard disks.)
- Parity (always saves two sets of parity information. In that way, associated data can be restored if one or two disks fail.)
- Storage Volume ((Number of hard drives - 2) x space of the smallest hard drive)
  - For example, with four 1GB hard disks, only 50% of their potential memory would be available to store user data. However, as the number of disks increases, this relationship between capacity and parity improves.
- Advantage over [[RAID 5|n.raid#raid-5]]
  - parity information to recover lost data is saved in duplicate. Duplicated parity data is a more efficient way of creating redundancy, and also ensures higher reliability.
  - This is less taxing on the remaining drives compared to ordinary

### RAID 50

- ![RAID 50](/assets/images/2022-03-12-16-28-30.png)
- Minimum of 6 drives

### RAID 60

- ![RAID 60](/assets/images/2022-03-12-16-30-23.png)

## Storage via ZFS

See [[n.zfs]]

## RAID-Z

TODO <https://www.diskinternals.com/raid-recovery/what-is-raidz/>
