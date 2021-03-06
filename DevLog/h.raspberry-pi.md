---
id: i5jlwl1lk5p3w0l1cuyosjh
title: Raspberry Pi
desc: ''
updated: 2022-03-12 2045
created: 2021-11-16 1520
---


- Raspberry Pi PLEX Home Media Server
  - [Main Resource](https://youtu.be/gyMpI8csWis)
  - KEY
    - **Noobs Install**
    - _ISO Install with Pi Installer_
  - **Using Noobs install Raspberry Pi OS Lite**
  - _Burn Raspberry Pi OS Lite to the SD card_
    - _In menu press `Shift + X` to open advanced settings and activate SSH, use Ethernet so DHCP auto assigns an IP Address to the Pi_
  - update password `passwd`
  - Update and Upgrade everything: `sudo apt-get update && sudo apt-get upgrade`
  - `sudo apt-get install vim`
  - Try to install SSH: `sudo apt-get install openssh-server`
  - Create SSH file: `touch /boot/ssh`
  - Activate SSH: 
    - `sudo raspi-config`
      - Interface Options
      - Enable SSH
    - OR
      - `sudo systemctl enable ssh`
      - `sudo systemctl start ssh`
  - Figure out IP Address to SSH into: `hostname -i`
  - [Install software for Cooling fan](https://wiki.geekworm.com/X735_V2.5_Software)
    - `sudo apt-get install -y python-smbus python`
    - `sudo apt-get install -y pigpio python-pigpio python3-pigpio git`
    - `git clone https://github.com/geekworm-com/x735-v2.5`
    - `cd x735-v2.5`
    - `sudo chmod +x *.sh`
    - `sudo bash install.sh`
    - `sudo reboot`
  - update `.bash_aliases`
    - `alias v='vim'`
    - `alias '..'='cd ..'`
    - `alias 'll'='ls -lA'`
  - Update `.bashrc`
    - add this so that at startup fan always starts: `python /home/pi/x735-v2.5/pwm_fan_control.py &`
  - Install OpenMediaVault: `wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash`
  - Go to the web location using the IP address of the pi in the URL location
  - OpenMediaVault (OMV) default creds:
    - username: admin
    - password: openmediavault
  - Update OMV credentials
    - System > General Settings > Web Administrator Password	
  - Make sure disk/drive is listed
    - Storage > Disks
  - Then To mount the drive
    - Storage > File Systems
    - Create
    - Select your device, Label for it, and `EXT4`
    - Mount
  - Provisioning
    - Access Rights Management > Shared Folder
    - Add
    - Name it, select the drive, name the folder, default credentials
    - Privileges
      - Make sure Pi (or any other user) can read/write
    - Apply
  - Now to set up some services
    - Services
      - SMB == Windows
        - Services > SMB > Settings > General Settings > Enable
        - Services > SMB > Shares > Create
          - Can leave them all default or modify later, just choose folder and that's MVP
      - NFS == Linux/MacOS
        - Services > NFS > Settings > Enable
        - Services > NFS > Shares > Create
  - User Access
    - Access Rights Management > User
    - Edit the Pi to use the same password as the system login
    - Hit Save if/when you get an error, acknowledge and then hit Save again
  - Map the network drives on the various computers using SMB
  - Starting Plex Server Setup
    - `sudo apt-get install apt-transport-https`
    - `curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -`
    - `echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list`
    - `sudo apt-get update`
    - `sudo apt install plexmediaserver`
      - When prompted for Which Repo version to use at around 40% completion, just say `N`
  - Go to the web address of your IP address plus port 32400/web to open Plex
  - Make a free account with plex and follow the prompts to set up your account

---

- Tags: 
  -
- Reference:
  -
- Related:
  -

