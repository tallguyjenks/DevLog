---
id: 23xvy5h0503jnwb51mhvvjv
title: Configuration
desc: ''
updated: 1650063675295
created: 1646726626690
---

## Link Aggregation

[[n.link-aggregation]] / [[n.protocol.lacp]]

in the console follow the prompts to add all current interfaces to a `lagg` using [[n.protocol.lacp]], Then configure the aggregation for [[n.protocol.dhcp]]

Now the web console should be available at a listed IP Address

## Configure SMART Tests

- `Tasks > S.M.A.R.T Test > Add`

```txt
All Disks
Type: LONG
Description: Long SMART test
Schedule: Monthly (0 0 1 * *) on the first day of the month at 00:00 (12:00 AM)
SAVE
```

## Hardening

- <https://www.truenas.com/docs/scale/communityrecommends/hardened-backup-repository-for-veeam/#configure-smart-tests>

1. Use Fixed IP Address not DHCP
2. Disable Service Announcement
   - NetBIOS-NS
   - mDNS
   - WS-Discovery
3. use well known DNS servers
   - `1.1.1.1`
   - `8.8.8.8`
4. Keep 1 interface for management layer and 3 interfaces in [[n.protocol.lacp]] for data
5. `System > General > web interface address`
   - use [[n.protocol.https]] redirect
6. make [[n.protocol.ssh]] NOT start automatically.
   - And in the advanced settings `ssh > pencil icon > advanced > auxillary parameters`
     - add `AllowUsers root@#.#.#.#` where `#.#.#.#` is the IP Address of the computer you want to be able to [[n.protocol.ssh]] from
7. Give root an email for those important notifications
   - configure the notifications 

## Configure Users and groups for shared volumes

- <https://www.truenas.com/community/threads/how-to-set-up-truenas-from-beginning-to-end-including-secure-remote-access-to-files-and-web-gui.89229/>

- To create shared volumes you can access through connection to your local network, see the following instructions.
  - Go to accounts on the left panel.
    - Click on groups.
    - Click add.
    - Enter a group name (you can leave the GID as it is).
    - Enable permit sudo and samba authentication.
    - Submit.
    - Go to accounts on the left panel.
    - Click on users.
    - Click add.
    - Fill in all the empty field under Identification
    - Uncheck new primary group.
    - Choose the group you made previously from the drop down menu in primary groups.
    - Go ahead and check all of the boxes under Home Directory Permissions.
    - Under Authentication check permit sudo and Samba authentication.
    - Submit.
    - Go to Storage -> Pools
    - Click add.
      - Select create new pool then click create pool.
    - Go back to Storage -> Pools
    - You should see the name of your new pool pop up.
    - Click on the three dots on the right side of that name.
      - Click add Zvol (this must be done!)
      - Put in a name and select a size for the Zvol (for a 1TB drive I used 1 GB, this is block device mainly used for VMs, so you can use less if you don't plan on using VMs on your NAS, more if you do).
      - Click submit.
    - Click on the three dots on the right side of the pool once again.
      - Click add dataset.
      - Type in a name and click submit.
    - Now you should be able to see the name of that dataset underneath your pool in Storage -> Pools
    - Click on the three dots on the right side of the name of the dataset.
      - Click on permissions.
      - Set the user under owner to www and group to www.
      - Click apply user and apply group.
      - Under access mode, check all of the boxes.
      - Click apply permissions recursively under advanced.
      - Click save.
    - Click on the three dots on the right side of the name of the dataset.
      - Click on permissions.
      - Click on ACL manager.
      - Click on the preset open under the dropdown menu.
      - Set the user under owner to www and group to www.
      - Click apply user and apply group.
      - Click apply permissions recursively under advanced.
      - Click save
    - Go to Services
      - Enable SMB and click on start automatically.
    - Go to Sharing -> Windows Shares (SMB)
      - Click add.
        - Select the path to your dataset.
        - Click submit.
    - Now to access this folder from your Windows machine on your local network.
      - Go to file explorer -> network
      - Click on the top field and enter the IP address of your TrueNAS machine in this fashion (should be the same as the IP address you used to connect to your WebGUI)
        - `\\youripaddress`
      - When it asks for username and password, use the username of the new account you created in the WebGUI and its password.
      - If you see your folder, great! If not, refer back to the previous steps to see if you did anything wrong.




