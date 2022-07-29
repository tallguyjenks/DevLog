

## rsync for system backups

### General syntax for dummies

> rsync [options] from [to]

### Tags im using and what they do

- **-a** _Archive mode_
- **-A** _Preserved Active control Lists (ACL's)_
- **-X** _Preserves extended attributes_
- **-v** _Verbose output of actions_
- **-z** _Compress files in transit_

### Extended Flags

- **--delete** _Files deleted from FROM removed from TO without being explicitly cited_
- **--exclude={/home/bryan/example/\*}** _Exclude files from specific directories_

### My 'FROM' Directory

`/home/bryan`

### My 'TO' Location

> _Must mount the backup storage device for external backup_

`/mnt/`
