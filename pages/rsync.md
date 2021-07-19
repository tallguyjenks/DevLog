# rsync for system backups
## General syntax for dummies

> rsync [options] from [to]
- ## Tags im using and what they do
- **-a** *Archive mode*
- **-A** *Preserved Active control Lists (ACL's)*
- **-X** *Preserves extended attributes*
- **-v** *Verbose output of actions*
- **-z** *Compress files in transit*
- ## Extended Flags
- **--delete** *Files deleted from FROM removed from TO without being explicitly cited*
- **--exclude={/home/bryan/example/\*}** *Exclude files from specific directories*
- ## My 'FROM' Directory
  
  `/home/bryan`
## My 'TO' Location 
> *Must mount the backup storage device for external backup*

`/mnt/`